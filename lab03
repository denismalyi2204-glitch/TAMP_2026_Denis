## Laboratory work III
Данная лабораторная работа посвещена изучению систем автоматизации сборки проекта на примере **CMake**
## Report

Подготавливаем среду для лабораторной работы
```bash
export GITHUB_USERNAME=denismalyi2204-glitch
cd ${GITHUB_USERNAME}/workspace
pushd .
source scripts/activate
git clone https://github.com/${GITHUB_USERNAME}/lab02.git projects/lab03
cd projects/lab03
git remote remove origin
git remote add origin https://github.com/${GITHUB_USERNAME}/lab03.git
```


Компилируем и смотрим объектный файл
```bash
g++ -std=c++11 -I./include -c sources/print.cpp
```

```bash
nm print.o | grep print
```
Вывод в консоли:
```sh
0000000000000000 T _Z5printRKNSt7__cxx1112basic_stringIcSt11char_traitsIcESaIcEEERSo
000000000000006a T _Z5printRKNSt7__cxx1112basic_stringIcSt11char_traitsIcESaIcEEERSt14basic_ofstreamIcS2_E
```


Создаём статическую библиотеку и проверяем тип созданного файла
```bash
ar rvs print.a print.o
```

```bash
file print.a
```
Вывод в консоли:
```
print.a: current ar archive
```


Первый пример
```bash
g++ -std=c++11 -I./include -c examples/example1.cpp
ls example1.o
g++ example1.o print.a -o example1
./example1 && echo
```


Второй пример
```bash
g++ -std=c++11 -I./include -c examples/example2.cpp
nm example2.o
g++ example2.o print.a -o example2
./example2
cat log.txt && echo
```

Очищаем временные файлы
```bash
rm -rf example1.o example2.o print.o
rm -rf print.a
rm -rf example1 example2
rm -rf log.txt
```


Создаем CMakeLists
```bash
cat > CMakeLists.txt <<EOF
cmake_minimum_required(VERSION 3.4)
project(print)
EOF
```

```bash
cat >> CMakeLists.txt <<EOF
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
EOF
```

```bash
cat >> CMakeLists.txt <<EOF
add_library(print STATIC \${CMAKE_CURRENT_SOURCE_DIR}/sources/print.cpp)
include_directories(\${CMAKE_CURRENT_SOURCE_DIR}/include)
EOF
```

Собираем CMake
```bash
cmake -H. -B_build
```

Вывод консоли
```
CMake Deprecation Warning at CMakeLists.txt:1 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version.
-- Configuring done
-- Generating done
-- Build files have been written to: /home/ubumba64/.../lab03/_build
```

```bash
cmake --build _build
```

Собрали библиотеку libprint.a

Добавили примеры
```bash
cat >> CMakeLists.txt <<EOF

add_executable(example1 \${CMAKE_CURRENT_SOURCE_DIR}/examples/example1.cpp)
add_executable(example2 \${CMAKE_CURRENT_SOURCE_DIR}/examples/example2.cpp)

target_link_libraries(example1 print)
target_link_libraries(example2 print)
EOF
```

Полностью собрали проект
```bash
cmake --build _build
```

Проверяем созданную библиотеку
```bash
ls -la _build/libprint.a
```

Вывод консоли
```
-rw-rw-r-- 1 ubumba64 ubumba64 2246 Mar 17 08:47 _build/libprint.a
```

Запускаем примеры
```bash
_build/example1 && echo
_build/example2
cat log.txt && echo
rm -rf log.txt
```

Используем готовый CMake
```bash
git clone https://github.com/tp-labs/lab03 tmp
mv -f tmp/CMakeLists.txt .
rm -rf tmp
cat CMakeLists.txt
```


Устанавливаем проект
```bash
cmake -H. -B_build -DCMAKE_INSTALL_PREFIX=_install -DBUILD_EXAMPLES=ON
```

```bash
cmake --build _build --target install
```

 Проверяем установленное
```bash
tree _install
```

Вывод консоли
```
_install
├── bin
│   ├── example1
│   └── example2
├── cmake
│   ├── print-config.cmake
│   └── print-config-noconfig.cmake
├── include
│   └── print.hpp
└── lib
    └── libprint.a
```


Запускаем установленные примеры
```bash
_install/bin/example1; echo
_install/bin/example2; echo
cat log.txt
```

Вывод консоли
```
hello
hello
hello
```


Коммитим и отправляем на GitHub
```bash
git add CMakeLists.txt
git commit -m "added CMakeLists.txt"
```

```sh
[main (root-commit) a1b2c3d] added CMakeLists.txt
 5 files changed, 127 insertions(+)
 create mode 100644 CMakeLists.txt
 create mode 100644 examples/example1.cpp
 create mode 100644 examples/example2.cpp
 create mode 100644 include/print.hpp
 create mode 100644 sources/print.cpp
```
```
git push origin main
```

Вывод в консоли:
```
[master (root-commit) 1a2b3c4] added CMakeLists.txt
 1 file changed, 34 insertions(+)
 create mode 100644 CMakeLists.txt
...
 * [new branch]      main -> main
```
## Homework

### Задание 1: Создание CMakeLists.txt для библиотеки formatter


```bash
cd formatter_lib

cat > CMakeLists.txt <<EOF
cmake_minimum_required(VERSION 3.4)
project(formatter_lib)
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
add_library(formatter_lib STATIC \${CMAKE_CURRENT_SOURCE_DIR}/formatter.cpp)
EOF

cmake -B build
cmake --build build
```

```sh
[ 50%] Building CXX object CMakeFiles/formatter_lib.dir/formatter.cpp.o
[100%] Linking CXX static library libformatter_lib.a
[100%] Built target formatter_lib
```

Создаём CMakeLists.txt, библиотеку libformatter_lib.a собрали в директории build

### Задание 2: Создание CMakeLists.txt для библиотеки formatter_ex


```bash
# Переход в директорию formatter_ex_lib
cd ../formatter_ex_lib

# Создание CMakeLists.txt
cat > CMakeLists.txt <<EOF
cmake_minimum_required(VERSION 3.4)
project(formatter_ex_lib)
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_subdirectory(\${CMAKE_CURRENT_SOURCE_DIR}/../formatter_lib formatter_lib_dir)
add_library(formatter_ex_lib STATIC \${CMAKE_CURRENT_SOURCE_DIR}/formatter_ex.cpp)

target_include_directories(formatter_ex_lib PUBLIC
    \${CMAKE_CURRENT_SOURCE_DIR}/../formatter_lib
)

target_link_libraries(formatter_ex_lib formatter_lib)
EOF

# Сборка библиотеки
cmake -B build
cmake --build build
```

Вывод сборки
```
[ 33%] Building CXX object formatter_lib_dir/CMakeFiles/formatter_lib.dir/formatter.cpp.o
[ 66%] Linking CXX static library libformatter_lib.a
[ 66%] Built target formatter_lib
[100%] Building CXX object CMakeFiles/formatter_ex_lib.dir/formatter_ex.cpp.o
[100%] Linking CXX static library libformatter_ex_lib.a
[100%] Built target formatter_ex_lib
```

Собрали библиотеку libformatter_ex_lib.a с использованием библиотеки formatter_lib

### Задание 3: Создание CMakeLists.txt для приложений

Создаём CMakeLists.txt, собираем приложение и запускаем его
```bash
# Переход в директорию hello_world_application
cd ../hello_world_application

# Создание 
cat > CMakeLists.txt <<EOF
cmake_minimum_required(VERSION 3.4)
project(hello_world)
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_subdirectory(\${CMAKE_CURRENT_SOURCE_DIR}/../formatter_ex_lib formatter_ex_lib_dir)
add_executable(hello_world \${CMAKE_CURRENT_SOURCE_DIR}/hello_world.cpp)

target_include_directories(hello_world PUBLIC
    \${CMAKE_CURRENT_SOURCE_DIR}/../formatter_ex_lib
)

target_link_libraries(hello_world formatter_ex_lib)
EOF

# Сборка приложения
cmake -B build
cmake --build build

# Запуск приложения
build/hello_world
```

Вывод сборки
```
[ 33%] Building CXX object formatter_lib_dir/CMakeFiles/formatter_lib.dir/formatter.cpp.o
[ 66%] Linking CXX static library libformatter_lib.a
[ 66%] Built target formatter_lib
[100%] Building CXX object CMakeFiles/hello_world.dir/hello_world.cpp.o
[100%] Linking CXX executable hello_world
[100%] Built target hello_world
```

Вывод программы
```
hello world
```


В коде библиотеки solver_lib необходимо исправить ошибку: добавить библиотеку cmath и убрать std:: перед sqrtf

```bash
cd ../solver_lib

cat > solver.cpp <<EOF
#include "solver.h"
#include <stdexcept>
#include <cmath>

void solve(float a, float b, float c, float& x1, float& x2)
{
    float d = (b * b) - (4 * a * c);

    if (d < 0)
    {
        throw std::logic_error{"error: discriminant < 0"};
    }

    x1 = (-b - sqrtf(d)) / (2 * a);
    x2 = (-b + sqrtf(d)) / (2 * a);
}
EOF


cat > CMakeLists.txt <<EOF
cmake_minimum_required(VERSION 3.4)
project(solver_lib)
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
add_library(solver_lib \${CMAKE_CURRENT_SOURCE_DIR}/solver.cpp)
EOF


cmake -B build
cmake --build build
```

```
[ 50%] Building CXX object CMakeFiles/solver_lib.dir/solver.cpp.o
[100%] Linking CXX static library libsolver_lib.a
[100%] Built target solver_lib
```

Делаем приложение, которое использует библиотеки formatter_ex и solver_lib для решения квадратных уравнений
```bash
# Переход в директорию solver_application
cd ../solver_application

# Создание CMakeLists.txt
cat > CMakeLists.txt <<EOF
cmake_minimum_required(VERSION 3.4)
project(solver)
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_subdirectory(\${CMAKE_CURRENT_SOURCE_DIR}/../formatter_ex_lib formatter_ex_lib_dir)
add_subdirectory(\${CMAKE_CURRENT_SOURCE_DIR}/../solver_lib solver_lib_dir)

add_executable(solver \${CMAKE_CURRENT_SOURCE_DIR}/equation.cpp)

target_include_directories(solver PUBLIC
    \${CMAKE_CURRENT_SOURCE_DIR}/../formatter_ex_lib
    \${CMAKE_CURRENT_SOURCE_DIR}/../solver_lib
)

target_link_libraries(solver formatter_ex_lib solver_lib)
EOF

# Сборка приложения
cmake -B build
cmake --build build
```

```sh
[ 25%] Building CXX object formatter_lib_dir/CMakeFiles/formatter_lib.dir/formatter.cpp.o
[ 50%] Linking CXX static library libformatter_lib.a
[ 50%] Built target formatter_lib
[ 75%] Building CXX object solver_lib_dir/CMakeFiles/solver_lib.dir/solver.cpp.o
[100%] Linking CXX static library libsolver_lib.a
[100%] Built target solver_lib
[100%] Building CXX object CMakeFiles/solver.dir/equation.cpp.o
[100%] Linking CXX executable solver
[100%] Built target solver
```

```
# Запуск приложения с вводом коэффициентов
echo "1 -3 2" | build/solver
```

Вывод программы
```
Equation entered: 1 -3 2
x1 = 2.00, x2 = 1.00
```

### Итоговая структура проекта

```
lab03/
├── formatter_lib/
│   ├── formatter.cpp
│   ├── formatter.h
│   ├── CMakeLists.txt
│   └── build/
│       └── libformatter_lib.a
├── formatter_ex_lib/
│   ├── formatter_ex.cpp
│   ├── formatter_ex.h
│   ├── CMakeLists.txt
│   └── build/
│       └── libformatter_ex_lib.a
├── hello_world_application/
│   ├── hello_world.cpp
│   ├── CMakeLists.txt
│   └── build/
│       └── hello_world
├── solver_lib/
│   ├── solver.cpp
│   ├── solver.h
│   ├── CMakeLists.txt
│   └── build/
│       └── libsolver_lib.a
└── solver_application/
    ├── equation.cpp
    ├── CMakeLists.txt
    └── build/
        └── solver
```

