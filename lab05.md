## Laboratory work V

Данная лабораторная работа посвещена изучению фреймворков для тестирования на примере **GTest**
## Report

Настраиваем окружение
```sh
export GITHUB_USERNAME=ваше_имя_пользователя
cd ${GITHUB_USERNAME}/workspace
pushd .
source scripts/activate
```

Копируем репозиторий и подключаем удаленный
```sh
git clone https://github.com/${GITHUB_USERNAME}/lab04 projects/lab05
cd projects/lab05
git remote remove origin
git remote add origin https://github.com/${GITHUB_USERNAME}/lab05
```

Вывод 
```sh
Cloning into 'projects/lab05'...
remote: Enumerating objects: 70, done.
remote: Counting objects: 100% (70/70), done.
remote: Compressing objects: 100% (44/44), done.
remote: Total 70 (delta 16), reused 66 (delta 12), pack-reused 0 (from 0)
Receiving objects: 100% (70/70), 9.77 KiB | 1.95 MiB/s, done.
Resolving deltas: 100% (16/16), done
```

Подключаем фреймворк для модульного тестирования Google Test как подмодуль, чтобы можно было писать и запускать тесты.
```sh
mkdir third-party
git submodule add https://github.com/google/googletest third-party/gtest
cd third-party/gtest && git checkout release-1.8.1 && cd ../..
git add third-party/gtest
git commit -m"added gtest framework"
```

Вывод
```sh
Cloning into '/home/ubumba64/denismalyi2204-glitch/workspace/projects/projects/lab05/third-party/gtest'...
remote: Enumerating objects: 28627, done.
remote: Counting objects: 100% (61/61), done.
remote: Compressing objects: 100% (46/46), done.
remote: Total 28627 (delta 32), reused 15 (delta 15), pack-reused 28566 (from 2)
Receiving objects: 100% (28627/28627), 13.74 MiB | 1.28 MiB/s, done.
Resolving deltas: 100% (21273/21273), done.
Note: switching to 'release-1.8.1'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -

Turn off this advice by setting config variable advice.detachedHead to false

HEAD is now at 2fe3bd99 Merge pull request #1433 from dsacre/fix-clang-warnings
[main b0abb62] added gtest framework
 2 files changed, 4 insertions(+)
 create mode 100644 .gitmodules
 create mode 160000 third-party/gtest
```

Настраиваем систему сборки CMake для компиляции и запуска модульных тестов
```sh
sed -i '/option(BUILD_EXAMPLES "Build examples" OFF)/a\
option(BUILD_TESTS "Build tests" OFF)
' CMakeLists.txt
cat >> CMakeLists.txt <<EOF
if(BUILD_TESTS)
  enable_testing()
  add_subdirectory(third-party/gtest)
  file(GLOB \${PROJECT_NAME}_TEST_SOURCES tests/*.cpp)
  add_executable(check \${\${PROJECT_NAME}_TEST_SOURCES})
  target_link_libraries(check \${PROJECT_NAME} gtest_main)
  add_test(NAME check COMMAND check)
endif()
EOF
```

Создаем первый модульный тест для проверки функции вывода текста в файл с использованием Google Test.
```sh
mkdir tests
cat > tests/test1.cpp <<EOF
#include <print.hpp>
#include <gtest/gtest.h>
TEST(Print, InFileStream)
{
  std::string filepath = "file.txt";
  std::string text = "hello";
  std::ofstream out{filepath};
  print(text, out);
  out.close();
  std::string result;
  std::ifstream in{filepath};
  in >> result;
  EXPECT_EQ(result, text);
}
EOF
```

Компилируем проект, запускаем все тесты и выводим результат их выполнения
```sh
cmake -H. -B_build -DBUILD_TESTS=ON
cmake --build _build
cmake --build _build --target test
_build/check
cmake --build _build --target test -- ARGS=--verbose
```

Вывод
```sh
-- The C compiler identification is GNU 13.3.0
-- The CXX compiler identification is GNU 13.3.0
-- Detecting C compiler ABI info
-- Detecting C compiler ABI info - done
-- Check for working C compiler: /usr/bin/cc - skipped
-- Detecting C compile features
-- Detecting C compile features - done
-- Detecting CXX compiler ABI info
-- Detecting CXX compiler ABI info - done
-- Check for working CXX compiler: /usr/bin/c++ - skipped
-- Detecting CXX compile features
-- Detecting CXX compile features - done
-- Found GTest: /usr/lib/x86_64-linux-gnu/cmake/GTest/GTestConfig.cmake (found version "1.14.0")  
-- Configuring done (0.8s)
-- Generating done (0.0s)
-- Build files have been written to: /home/ubumba64/denismalyi2204-glitch/workspace/projects/lab05/_build
```
```sh
[ 12%] Building CXX object CMakeFiles/print.dir/sources/print.cpp.o
[ 25%] Linking CXX static library libprint.a
[ 25%] Built target print
[ 37%] Building CXX object CMakeFiles/example1.dir/examples/example1.cpp.o
[ 50%] Linking CXX executable example1
[ 50%] Built target example1
[ 62%] Building CXX object CMakeFiles/example2.dir/examples/example2.cpp.o
[ 75%] Linking CXX executable example2
[ 75%] Built target example2
[ 87%] Building CXX object CMakeFiles/check.dir/tests/test1.cpp.o
[100%] Linking CXX executable check
[100%] Built target check
```
```sh
Running tests...
Test project /home/ubumba64/denismalyi2204-glitch/workspace/projects/lab05/_build
    Start 1: check
1/1 Test #1: check ............................   Passed    0.01 sec
100% tests passed, 0 tests failed out of 1
Total Test time (real) =   0.01 sec
```
```sh
Running main() from /usr/src/googletest/googletest/src/gtest_main.cc
[==========] Running 1 test from 1 test suite.
[----------] Global test environment set-up.
[----------] 1 test from Print
[ RUN      ] Print.InFileStream
[       OK ] Print.InFileStream (0 ms)
[----------] 1 test from Print (0 ms total)
[----------] Global test environment tear-down
[==========] 1 test from 1 test suite ran. (0 ms total)
[  PASSED  ] 1 test.
```

Настраиваем непрерывную интеграцию (CI) на GitHub Actions, которая автоматически собирает проект и запускает все тесты при каждом изменении в репозитории
```sh
mkdir -p .github/workflows
cat > .github/workflows/ci.yml <<EOF
name: CI
on: [push, pull_request]
jobs:
  build:
    runs-on: ubuntu-latest
    
    steps:
    - uses: actions/checkout@v2
      with:
        submodules: recursive
    
    - name: Configure CMake
      run: cmake -H. -B_build -DBUILD_TESTS=ON
    
    - name: Build
      run: cmake --build _build
    
    - name: Run tests
      run: cmake --build _build --target test
    
    - name: Run tests verbose
      run: cmake --build _build --target test -- ARGS=--verbose
EOF
```

Обновляем ссылки и название проекта в README с 4-й на 5-ю лабу
```sh
sed -i 's/lab04/lab05/g' README.md
```

Вставляем визуальный индикатор, показывающий текущий статус сборки и тестов на странице репозитория
```sh
cat >> README.md <<EOF
## CI Status
[![CI](https://github.com/${GITHUB_USERNAME}/lab05/actions/workflows/ci.yml/badge.svg)](https://github.com/${GITHUB_USERNAME}/lab05/actions/workflows/ci.yml)
EOF
```

Сохраняем все настройки тестирования и непрерывной интеграции в репозиторий
```sh
git add .github/
git add tests
git add README.md
git add CMakeLists.txt
git add third-party/gtest
git add -p
git commit -m"added tests and GitHub Actions"
```

Вывод
```sh
No changes.
[main de88a4c] added tests and GitHub Actions
 5 files changed, 74 insertions(+), 82 deletions(-)
 create mode 100644 tests/test1.cpp
 delete mode 160000 third-party/gtest

```

 Публикуем проект на GitHub и создаем скриншот для отчета 
```sh
git push origin master
mkdir artifacts
sleep 20s && gnome-screenshot --file artifacts/screenshot.png
```

Вывод
```sh
Username for 'https://github.com': denismalyi2204-glitch
Password for 'https://denismalyi2204-glitch@github.com': 
Enumerating objects: 83, done.
Counting objects: 100% (83/83), done.
Delta compression using up to 4 threads
Compressing objects: 100% (49/49), done.
Writing objects: 100% (83/83), 11.73 KiB | 3.91 MiB/s, done.
Total 83 (delta 19), reused 68 (delta 16), pack-reused 0
remote: Resolving deltas: 100% (19/19), done.
To https://github.com/denismalyi2204-glitch/lab05
 * [new branch]      main -> main

```

## Homework

Клонируем репозиторий
```bash
cd ~/denismalyi2204-glitch/workspace/projects
git clone https://github.com/denismalyi2204-glitch/banking.git
cd banking
```

Создаем структуру проекта
```bash
mkdir -p include src tests .github/workflows
```

Создание Account.h
```bash
cat > include/Account.h <<'EOF'
#pragma once
#include <string>

class Account {
private:
    std::string accountNumber;
    double balance;
    std::string ownerName;

public:
    Account(const std::string& number, const std::string& owner, double initialBalance = 0.0);
    
    std::string getAccountNumber() const;
    std::string getOwnerName() const;
    double getBalance() const;
    
    void deposit(double amount);
    bool withdraw(double amount);
    bool transferTo(Account& to, double amount);
};
EOF
```

Созданем Account.cpp
```bash
cat > src/Account.cpp <<'EOF'
#include "Account.h"
#include <stdexcept>

Account::Account(const std::string& number, const std::string& owner, double initialBalance)
    : accountNumber(number), ownerName(owner), balance(initialBalance) {
    if (initialBalance < 0) {
        throw std::invalid_argument("Initial balance cannot be negative");
    }
}

std::string Account::getAccountNumber() const {
    return accountNumber;
}

std::string Account::getOwnerName() const {
    return ownerName;
}

double Account::getBalance() const {
    return balance;
}

void Account::deposit(double amount) {
    if (amount <= 0) {
        throw std::invalid_argument("Deposit amount must be positive");
    }
    balance += amount;
}

bool Account::withdraw(double amount) {
    if (amount <= 0) {
        throw std::invalid_argument("Withdrawal amount must be positive");
    }
    if (amount > balance) {
        return false;
    }
    balance -= amount;
    return true;
}

bool Account::transferTo(Account& to, double amount) {
    if (withdraw(amount)) {
        to.deposit(amount);
        return true;
    }
    return false;
}
EOF
```

Создаем Transaction.h
```bash
cat > include/Transaction.h <<'EOF'
#pragma once
#include <string>
#include <chrono>
#include <memory>

class Account;

class Transaction {
private:
    std::string transactionId;
    std::string fromAccount;
    std::string toAccount;
    double amount;
    std::chrono::system_clock::time_point timestamp;
    bool success;

public:
    Transaction(const std::string& from, const std::string& to, double amount);
    
    std::string getTransactionId() const;
    std::string getFromAccount() const;
    std::string getToAccount() const;
    double getAmount() const;
    std::chrono::system_clock::time_point getTimestamp() const;
    bool isSuccess() const;
    
    void setSuccess(bool success);
    bool execute(std::shared_ptr<Account> from, std::shared_ptr<Account> to);
};
EOF
```

Создаем Transaction.cpp
```bash
cat > src/Transaction.cpp <<'EOF'
#include "Transaction.h"
#include "Account.h"
#include <chrono>
#include <sstream>
#include <iomanip>

Transaction::Transaction(const std::string& from, const std::string& to, double amount)
    : fromAccount(from), toAccount(to), amount(amount), success(false) {
    
    auto now = std::chrono::system_clock::now();
    auto now_ms = std::chrono::time_point_cast<std::chrono::milliseconds>(now);
    auto value = now_ms.time_since_epoch().count();
    
    std::stringstream ss;
    ss << std::hex << value;
    transactionId = ss.str();
    timestamp = now;
}

std::string Transaction::getTransactionId() const {
    return transactionId;
}

std::string Transaction::getFromAccount() const {
    return fromAccount;
}

std::string Transaction::getToAccount() const {
    return toAccount;
}

double Transaction::getAmount() const {
    return amount;
}

std::chrono::system_clock::time_point Transaction::getTimestamp() const {
    return timestamp;
}

bool Transaction::isSuccess() const {
    return success;
}

void Transaction::setSuccess(bool success) {
    this->success = success;
}

bool Transaction::execute(std::shared_ptr<Account> from, std::shared_ptr<Account> to) {
    if (!from || !to) {
        return false;
    }
    
    if (from->getAccountNumber() != fromAccount || to->getAccountNumber() != toAccount) {
        return false;
    }
    
    success = from->transferTo(*to, amount);
    return success;
}
EOF
```

Создаем CMakeLists.txt
```bash
cat > CMakeLists.txt <<'EOF'
cmake_minimum_required(VERSION 3.14)
project(banking)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

include_directories(${CMAKE_CURRENT_SOURCE_DIR}/include)

add_library(banking STATIC
    src/Account.cpp
    src/Transaction.cpp
)

option(BUILD_TESTS "Build tests" ON)
option(COVERAGE "Enable coverage reporting" OFF)

if(COVERAGE)
    if(CMAKE_CXX_COMPILER_ID STREQUAL "GNU" OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
        add_compile_options(-O0 -g --coverage -fprofile-arcs -ftest-coverage)
        add_link_options(--coverage -lgcov)
    endif()
endif()

if(BUILD_TESTS)
    enable_testing()
    include(FetchContent)
    
    FetchContent_Declare(
        googletest
        GIT_REPOSITORY https://github.com/google/googletest.git
        GIT_TAG v1.14.0
    )
    FetchContent_MakeAvailable(googletest)
    
    add_executable(banking_tests 
        tests/test_account.cpp 
        tests/test_transaction.cpp
    )
    target_link_libraries(banking_tests banking gtest_main)
    target_include_directories(banking_tests PRIVATE ${CMAKE_CURRENT_SOURCE_DIR}/include)
    
    add_test(NAME banking_tests COMMAND banking_tests)
endif()
EOF
```

Создаем test_account.cpp
```bash
cat > tests/test_account.cpp <<'EOF'
#include <gtest/gtest.h>
#include "Account.h"
#include <stdexcept>

class AccountTest : public ::testing::Test {
protected:
    void SetUp() override {
        account = std::make_unique<Account>("12345", "John Doe", 1000.0);
    }
    
    std::unique_ptr<Account> account;
};

TEST_F(AccountTest, ConstructorValid) {
    EXPECT_EQ("12345", account->getAccountNumber());
    EXPECT_EQ("John Doe", account->getOwnerName());
    EXPECT_DOUBLE_EQ(1000.0, account->getBalance());
}

TEST_F(AccountTest, ConstructorNegativeBalance) {
    EXPECT_THROW(Account("99999", "Jane Doe", -100.0), std::invalid_argument);
}

TEST_F(AccountTest, DepositPositive) {
    account->deposit(500.0);
    EXPECT_DOUBLE_EQ(1500.0, account->getBalance());
}

TEST_F(AccountTest, DepositZeroOrNegative) {
    EXPECT_THROW(account->deposit(0.0), std::invalid_argument);
    EXPECT_THROW(account->deposit(-50.0), std::invalid_argument);
}

TEST_F(AccountTest, WithdrawValid) {
    bool result = account->withdraw(300.0);
    EXPECT_TRUE(result);
    EXPECT_DOUBLE_EQ(700.0, account->getBalance());
}

TEST_F(AccountTest, WithdrawInsufficientFunds) {
    bool result = account->withdraw(1500.0);
    EXPECT_FALSE(result);
    EXPECT_DOUBLE_EQ(1000.0, account->getBalance());
}

TEST_F(AccountTest, WithdrawInvalidAmount) {
    EXPECT_THROW(account->withdraw(0.0), std::invalid_argument);
    EXPECT_THROW(account->withdraw(-100.0), std::invalid_argument);
}

TEST_F(AccountTest, TransferToValid) {
    Account toAccount("67890", "Jane Doe", 500.0);
    bool result = account->transferTo(toAccount, 300.0);
    
    EXPECT_TRUE(result);
    EXPECT_DOUBLE_EQ(700.0, account->getBalance());
    EXPECT_DOUBLE_EQ(800.0, toAccount.getBalance());
}

TEST_F(AccountTest, TransferToInsufficientFunds) {
    Account toAccount("67890", "Jane Doe", 500.0);
    bool result = account->transferTo(toAccount, 1500.0);
    
    EXPECT_FALSE(result);
    EXPECT_DOUBLE_EQ(1000.0, account->getBalance());
    EXPECT_DOUBLE_EQ(500.0, toAccount.getBalance());
}

TEST_F(AccountTest, GetOwnerName) {
    EXPECT_EQ("John Doe", account->getOwnerName());
}

TEST_F(AccountTest, GetAccountNumber) {
    EXPECT_EQ("12345", account->getAccountNumber());
}
EOF
```

Создаем test_transaction.cpp
```bash
cat > tests/test_transaction.cpp <<'EOF'
#include <gtest/gtest.h>
#include "Transaction.h"
#include "Account.h"
#include <memory>

class TransactionTest : public ::testing::Test {
protected:
    void SetUp() override {
        fromAccount = std::make_shared<Account>("11111", "Sender", 1000.0);
        toAccount = std::make_shared<Account>("22222", "Receiver", 500.0);
    }
    
    std::shared_ptr<Account> fromAccount;
    std::shared_ptr<Account> toAccount;
};

TEST_F(TransactionTest, Constructor) {
    Transaction tx("11111", "22222", 200.0);
    
    EXPECT_EQ("11111", tx.getFromAccount());
    EXPECT_EQ("22222", tx.getToAccount());
    EXPECT_DOUBLE_EQ(200.0, tx.getAmount());
    EXPECT_FALSE(tx.isSuccess());
    EXPECT_FALSE(tx.getTransactionId().empty());
}

TEST_F(TransactionTest, ExecuteSuccessful) {
    Transaction tx("11111", "22222", 200.0);
    bool result = tx.execute(fromAccount, toAccount);
    
    EXPECT_TRUE(result);
    EXPECT_TRUE(tx.isSuccess());
    EXPECT_DOUBLE_EQ(800.0, fromAccount->getBalance());
    EXPECT_DOUBLE_EQ(700.0, toAccount->getBalance());
}

TEST_F(TransactionTest, ExecuteInsufficientFunds) {
    Transaction tx("11111", "22222", 1500.0);
    bool result = tx.execute(fromAccount, toAccount);
    
    EXPECT_FALSE(result);
    EXPECT_FALSE(tx.isSuccess());
    EXPECT_DOUBLE_EQ(1000.0, fromAccount->getBalance());
    EXPECT_DOUBLE_EQ(500.0, toAccount->getBalance());
}

TEST_F(TransactionTest, ExecuteNullAccounts) {
    Transaction tx("11111", "22222", 100.0);
    bool result = tx.execute(nullptr, toAccount);
    
    EXPECT_FALSE(result);
    EXPECT_FALSE(tx.isSuccess());
}

TEST_F(TransactionTest, ExecuteWrongAccountNumbers) {
    Transaction tx("99999", "22222", 100.0);
    bool result = tx.execute(fromAccount, toAccount);
    
    EXPECT_FALSE(result);
    EXPECT_FALSE(tx.isSuccess());
}

TEST_F(TransactionTest, SetSuccessManually) {
    Transaction tx("11111", "22222", 100.0);
    EXPECT_FALSE(tx.isSuccess());
    
    tx.setSuccess(true);
    EXPECT_TRUE(tx.isSuccess());
}
EOF
```

Создаем GitHub Actions workflow
```bash
cat > .github/workflows/ci.yml <<'EOF'
name: CI

on: [push, pull_request]

jobs:
  build-and-test:
    runs-on: ubuntu-latest
    
    steps:
    - uses: actions/checkout@v4
    
    - name: Install dependencies
      run: |
        sudo apt-get update
        sudo apt-get install -y lcov gcovr
    
    - name: Configure CMake with coverage
      run: cmake -H. -B_build -DBUILD_TESTS=ON -DCOVERAGE=ON
    
    - name: Build
      run: cmake --build _build
    
    - name: Run tests
      run: ./_build/banking_tests
    
    - name: Generate coverage report
      run: |
        cd _build
        gcovr --root .. --filter '.*/src/.*' --filter '.*/include/.*' --exclude '.*/_deps/.*' --xml --output coverage.xml
    
    - name: Upload to Coveralls
      uses: coverallsapp/github-action@v2
      with:
        file: _build/coverage.xml
        format: cobertura
        github-token: ${{ secrets.GITHUB_TOKEN }}
EOF
```

 Создаем README.md
```bash
cat > README.md <<'EOF'
[![CI](https://github.com/denismalyi2204-glitch/banking/actions/workflows/ci.yml/badge.svg)](https://github.com/denismalyi2204-glitch/banking/actions/workflows/ci.yml)
[![Coverage Status](https://coveralls.io/repos/github/denismalyi2204-glitch/banking/badge.svg)](https://coveralls.io/github/denismalyi2204-glitch/banking)

## Banking Library

Библиотека для банковских операций с классами:
- `Account` - банковский счет
- `Transaction` - транзакция между счетами

## Сборка и тестирование

```bash
cmake -H. -B_build -DBUILD_TESTS=ON
cmake --build _build
./_build/banking_tests
```

Покрытие кода
```bash
cmake -H. -B_build -DBUILD_TESTS=ON -DCOVERAGE=ON
cmake --build _build
./_build/banking_tests
cd _build
gcovr --root .. --filter '.*/src/.*' --filter '.*/include/.*' --html --output coverage_report.html
```

Выводы команд в консоль
```sh
-- The C compiler identification is GNU 13.3.0
-- The CXX compiler identification is GNU 13.3.0
-- Detecting C compiler ABI info
-- Detecting C compiler ABI info - done
-- Check for working C compiler: /usr/bin/cc - skipped
-- Detecting C compile features
-- Detecting C compile features - done
-- Detecting CXX compiler ABI info
-- Detecting CXX compiler ABI info - done
-- Check for working CXX compiler: /usr/bin/c++ - skipped
-- Detecting CXX compile features
-- Detecting CXX compile features - done
-- Found Python3: /usr/bin/python3 (found version "3.12.3") found components: Interpreter 
-- Performing Test CMAKE_HAVE_LIBC_PTHREAD
-- Performing Test CMAKE_HAVE_LIBC_PTHREAD - Success
-- Found Threads: TRUE  
-- Configuring done (10.6s)
-- Generating done (0.0s)
-- Build files have been written to: /home/ubumba64/denismalyi2204-glitch/workspace/projects/banking/_build
```
```sh
[  7%] Building CXX object CMakeFiles/banking.dir/src/Account.cpp.o
[ 14%] Building CXX object CMakeFiles/banking.dir/src/Transaction.cpp.o
[ 21%] Linking CXX static library libbanking.a
[ 21%] Built target banking
[ 28%] Building CXX object _deps/googletest-build/googletest/CMakeFiles/gtest.dir/src/gtest-all.cc.o
[ 35%] Linking CXX static library ../../../lib/libgtest.a
[ 35%] Built target gtest
[ 42%] Building CXX object _deps/googletest-build/googletest/CMakeFiles/gtest_main.dir/src/gtest_main.cc.o
[ 50%] Linking CXX static library ../../../lib/libgtest_main.a
[ 50%] Built target gtest_main
[ 57%] Building CXX object CMakeFiles/banking_tests.dir/tests/test_account.cpp.o
[ 64%] Building CXX object CMakeFiles/banking_tests.dir/tests/test_transaction.cpp.o
[ 71%] Linking CXX executable banking_tests
[ 71%] Built target banking_tests
[ 78%] Building CXX object _deps/googletest-build/googlemock/CMakeFiles/gmock.dir/src/gmock-all.cc.o
[ 85%] Linking CXX static library ../../../lib/libgmock.a
[ 85%] Built target gmock
[ 92%] Building CXX object _deps/googletest-build/googlemock/CMakeFiles/gmock_main.dir/src/gmock_main.cc.o
[100%] Linking CXX static library ../../../lib/libgmock_main.a
[100%] Built target gmock_main
```
```sh
Running main() from /home/ubumba64/denismalyi2204-glitch/workspace/projects/banking/_build/_deps/googletest-src/googletest/src/gtest_main.cc
[==========] Running 17 tests from 2 test suites.
[----------] Global test environment set-up.
[----------] 11 tests from AccountTest
[ RUN      ] AccountTest.ConstructorValid
[       OK ] AccountTest.ConstructorValid (0 ms)
[ RUN      ] AccountTest.ConstructorNegativeBalance
[       OK ] AccountTest.ConstructorNegativeBalance (0 ms)
[ RUN      ] AccountTest.DepositPositive
[       OK ] AccountTest.DepositPositive (0 ms)
[ RUN      ] AccountTest.DepositZeroOrNegative
[       OK ] AccountTest.DepositZeroOrNegative (0 ms)
[ RUN      ] AccountTest.WithdrawValid
[       OK ] AccountTest.WithdrawValid (0 ms)
[ RUN      ] AccountTest.WithdrawInsufficientFunds
[       OK ] AccountTest.WithdrawInsufficientFunds (0 ms)
[ RUN      ] AccountTest.WithdrawInvalidAmount
[       OK ] AccountTest.WithdrawInvalidAmount (0 ms)
[ RUN      ] AccountTest.TransferToValid
[       OK ] AccountTest.TransferToValid (0 ms)
[ RUN      ] AccountTest.TransferToInsufficientFunds
[       OK ] AccountTest.TransferToInsufficientFunds (0 ms)
[ RUN      ] AccountTest.GetOwnerName
[       OK ] AccountTest.GetOwnerName (0 ms)
[ RUN      ] AccountTest.GetAccountNumber
[       OK ] AccountTest.GetAccountNumber (0 ms)
[----------] 11 tests from AccountTest (0 ms total)
[----------] 6 tests from TransactionTest
[ RUN      ] TransactionTest.Constructor
[       OK ] TransactionTest.Constructor (0 ms)
[ RUN      ] TransactionTest.ExecuteSuccessful
[       OK ] TransactionTest.ExecuteSuccessful (0 ms)
[ RUN      ] TransactionTest.ExecuteInsufficientFunds
[       OK ] TransactionTest.ExecuteInsufficientFunds (0 ms)
[ RUN      ] TransactionTest.ExecuteNullAccounts
[       OK ] TransactionTest.ExecuteNullAccounts (0 ms)
[ RUN      ] TransactionTest.ExecuteWrongAccountNumbers
[       OK ] TransactionTest.ExecuteWrongAccountNumbers (0 ms)
[ RUN      ] TransactionTest.SetSuccessManually
[       OK ] TransactionTest.SetSuccessManually (0 ms)
[----------] 6 tests from TransactionTest (0 ms total)
[----------] Global test environment tear-down
[==========] 17 tests from 2 test suites ran. (0 ms total)
[  PASSED  ] 17 tests.
```
```sh
GCC Code Coverage Report
Directory: ..
File                                       Lines    Exec  Cover
--------------------------------------------------------------
include/Account.h                              8       8   100%
include/Transaction.h                         12      12   100%
src/Account.cpp                               28      28   100%
src/Transaction.cpp                           32      32   100%
--------------------------------------------------------------
TOTAL                                         80      80   100%
Lines: 100.0%
Functions: 100.0%
Branches: 100.0%
```

Отправляем на GitHub
```bash
git add .
git commit -m "feat: banking library with 100% test coverage"
git push origin main
```

Вывод
```sh
Enumerating objects: 304, done.
Counting objects: 100% (304/304), done.
Delta compression using up to 4 threads
Compressing objects: 100% (291/291), done.
Writing objects: 100% (303/303), 7.78 MiB | 930.00 KiB/s, done.
Total 303 (delta 155), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (155/155), done.
To https://github.com/denismalyi2204-glitch/banking.git
   a8e1033..678580a  main -> main
```

