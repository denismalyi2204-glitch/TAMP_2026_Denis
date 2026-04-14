## Laboratory work II

Данная лабораторная работа посвещена изучению систем контроля версий на примере **Git**.

## Report

```sh
$ export GITHUB_USERNAME=<имя_пользователя>
$ export GITHUB_EMAIL=<адрес_почтового_ящика>
$ export GITHUB_TOKEN=<сгенирированный_токен>
$ alias edit=subl
```
Устанавливаем переменные окружения и псевдоним для редактора

```sh
$ cd ${GITHUB_USERNAME}/workspace
$ source scripts/activate
```
Переходим в рабочую директорию

```sh
$ mkdir ~/.config
$ cat > ~/.config/hub <<EOF
github.com:
- user: ${GITHUB_USERNAME}
  oauth_token: ${GITHUB_TOKEN}
  protocol: https
EOF
$ git config --global hub.protocol https
```
Создаём конфигурационный файл для утилиты hub

```sh
$ mkdir projects/lab02 && cd projects/lab02
$ git init
Initialized empty Git repository in /home/denismalyi2204/projects/lab02/.git/
```
Создаём локальный репозиторий

```sh
$ git config --global user.name ${GITHUB_USERNAME}
$ git config --global user.email ${GITHUB_EMAIL}
# check your git global settings
$ git config -e --global
```
Настраиваем пользователя Git

```sh
$ git remote add origin https://github.com/${GITHUB_USERNAME}/lab02.git
$ git pull origin master
```

```sh
warning: no common commits
remote: Enumerating objects: 3, done.
remote: Counting objects: 100% (3/3), done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (3/3), done.
From https://github.com/denismalyi2204/lab02
 * branch            master     -> FETCH_HEAD
 * [new branch]      master     -> origin/master
```
Вывод

Привязываем удаленный репозиторий к локальному с именем origin и совмещаем их

```sh
$ touch README.md
$ git status
$ git add README.md
```

```
$ git commit -m"added README.md"
```

```sh
[master (root-commit) 929b610] added README.md
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 README.md
```
Вывод
```
$ git push origin master
```

```sh
Username for 'https://github.com': denismalyi2204
Password for 'https://denismalyi2204@github.com': 
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Writing objects: 100% (3/3), 210 bytes | 210.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
To https://github.com/denismalyi2204/lab02.git
 * [new branch]      master -> master
```
Вывод

Добавляем файл, смотрим изменения, добавляем изменения в индекс, коммитим и отправляем на удаленный репозиторий

```sh

commit fba7f71329c511bb0c18f1b111067780cf5b12d8 (HEAD -> main, origin/main)
Author: denismalyi2204 <denismalyi2204@gmail.com>
Date:   Sun Mar 8 18:27:06 2026 +0000

    added sources

commit eef56073c728a0d0c46ad80ef47191d1e03d9465
Author: denismalyi2204 <denismalyi2204@gmail.com>
Date:   Sun Mar 8 18:20:15 2026 +0000

    added .gitignore

commit 929b6106f18111b29450a5dff65c24955dcc90f3
Author: denismalyi2204 <denismalyi2204@gmail.com>
Date:   Sun Mar 8 18:13:51 2026 +0000

    added README.md

commit 7f450474f8447df8eacd90f5785308482930b2b8
Author: Denis <denismalyi2204@gmail.com>
Date:   Sun Mar 8 20:47:00 2026 +0300

    Initial commit
```

```sh
Username for 'https://github.com': denismalyi2204
Password for 'https://denismalyi2204@github.com': 

Enumerating objects: 12, done.
Counting objects: 100% (12/12), done.
Delta compression using up to 4 threads
Compressing objects: 100% (8/8), done.
Writing objects: 100% (10/10), 1.22 KiB | 1.22 MiB/s, done.
Total 10 (delta 0), reused 0 (delta 0), pack-reused 0
To https://github.com/denismalyi2204-glitch/lab02.git
   eef5607..fba7f71  main -> main
```

```sh
$ cd ~/workspace/
$ export LAB_NUMBER=02
$ git clone https://github.com/tp-labs/lab${LAB_NUMBER}.git tasks/lab${LAB_NUMBER}
```

```sh
Cloning into 'tasks/lab02'...
remote: Enumerating objects: 123, done.
remote: Counting objects: 100% (123/123), done.
remote: Compressing objects: 100% (45/45), done.
remote: Total 123 (delta 78), reused 102 (delta 62), pack-reused 0
Receiving objects: 100% (123/123), 45.67 KiB | 1.14 MiB/s, done.
Resolving deltas: 100% (78/78), done.
```
Вывод
```sh
$ mkdir reports/lab${LAB_NUMBER}
$ cp tasks/lab${LAB_NUMBER}/README.md reports/lab${LAB_NUMBER}/REPORT.md
$ cd reports/lab${LAB_NUMBER}
$ edit REPORT.md
$ gist REPORT.md
```
Далее создаем папки, в них создаем файлы cpp, затем коммитим их

С помощью gist пишем репорт

## Homework

### Часть I

   ```
   git clone https://github.com/denismalyi2204-glitch/cpp-hello-world.git
   cd cpp-hello-world
   echo "# TP-lab02" >> README.md
   git add README.md
   git commit -m "first commit"
   git branch -M main
   git push -u origin main
   ```

```sh
Username for 'https://github.com': denismalyi2204
Password for 'https://denismalyi2204@github.com': 
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Writing objects: 100% (3/3), 227 bytes | 227.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
To https://github.com/denismalyi2204-glitch/cpp-hello-world.git
 * [new branch]      main -> main
Branch 'main' set up to track remote branch 'main' from 'origin'.
```
Вывод

Выполнено клонирование пустого репозитория, первый коммит, создали файл README.md, отправили изменения на удалённый репозиторий


   ```
   nano hello_world.cpp
   ```

   ```cpp
   #include <iostream>
   using namespace std;
   
   int main() {   
	   cout << "Hello, World!" << endl;     
	   return 0;
   }
   ```
   
   ```sh
   git add hello_world.cpp
   git commit -m "added hello_world.cpp"
   ```

```sh
[main eef5607] added hello_world.cpp
 1 file changed, 9 insertions(+)
 create mode 100644 hello_world.cpp
```
Создали файл hello_world.cpp, реализовали программу "Hellow world" с умышленным плохим стилем, файл закоммичен с сообщением


   ```cpp
   #include <iostream>
   #include <string>
   using namespace std;
   
   int main() { 
	   string name; 
	   cout << "Please enter name: ";    
	   cin >> name;      
	   cout << "Hello world from " << name;
   }
   ```
   
   ```
   git add hello_world.cpp
   git commit -m "updated hello_world.cpp to ask for name"
   ```
 Обновили код для запроса имени пользователя, также закоммитили изменения


   ```
   git push origin main
   ```

```sh
Username for 'https://github.com': denismalyi2204
Password for 'https://denismalyi2204@github.com': 
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 4 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 351 bytes | 351.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
To https://github.com/denismalyi2204-glitch/cpp-hello-world.git
   7f45047..eef5607  main -> main
```
Вывод

 Отправили изменения на удалённый репозиторий

### Часть II

   ```
   git branch patch1
   git checkout patch1
   ```
 Создали локальную ветку patch1, переключились на неё



   ```
   nano hello_world.cpp
   ```

   ```cpp
   #include <iostream>
   #include <string>
   
   int main() {
       std::string name;
       std::cout << "Please enter name: ";
       std::cin >> name;
       std::cout << "Hello world from " << name;
   }
   ```
   ```
   git add hello_world.cpp
   git commit -m "patched hello_world.cpp"
   git push origin patch1
   ```

```sh
Username for 'https://github.com': denismalyi2204
Password for 'https://denismalyi2204@github.com': 
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 4 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 345 bytes | 345.00 KiB/s, done.
Total 3 (delta 2), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
remote: 
remote: Create a pull request for 'patch1' on GitHub by visiting:
remote:      https://github.com/denismalyi2204-glitch/cpp-hello-world/pull/new/patch1
remote: 
To https://github.com/denismalyi2204-glitch/cpp-hello-world.git
 * [new branch]      patch1 -> patch1
```
 В ветке `patch1` исправили код: убрали директиву using namespace std, добавили префиксы std::, закоммитили, отправили на удалённый репозиторий

Создали pull request, изменения корректны


   ```
   nano hello_world.cpp
   ```
   
   ```cpp
   #include <iostream>
   #include <string>
   
   int main() {
       std::string name;
       // Запрос имени пользователя
       std::cout << "Please enter name: ";
       std::cin >> name;
       // Вывод приветствия
       std::cout << "Hello world from " << name;
   }
   ```
   ```
   git add hello_world.cpp
   git commit -m "added comment"
   git push origin patch1
   ```

```sh
Username for 'https://github.com': denismalyi2204
Password for 'https://denismalyi2204@github.com': 
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 4 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 334 bytes | 334.00 KiB/s, done.
Total 3 (delta 2), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
To https://github.com/denismalyi2204-glitch/cpp-hello-world.git
   fba7f71..77ef672  patch1 -> patch1
```
Вывод

В ветке `patch1` добавили комментарии к коду, закоммитили изменения, выполнили push в удалённую ветку


   ```sh
   git checkout main
   Switched to branch 'main' 
   Your branch is up to date with 'origin/main'.
   git pull origin main
   ```

```sh
remote: Enumerating objects: 1, done.
remote: Counting objects: 100% (1/1), done.
remote: Total 1 (delta 0), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (1/1), 881 bytes | 881.00 KiB/s, done.
From https://github.com/denismalyi2204-glitch/cpp-hello-world
 * branch            main       -> FETCH_HEAD
   77ef672..abc1234  main       -> origin/main
Updating eef5607..abc1234
Fast-forward
 hello_world.cpp | 2 +-
 1 file changed, 1 insertion(+), 1 deletion(-)
```
Вывод
   ```sh   
   git branch -d patch1
   Deleted branch patch1 (was 77ef672).
   ```
На GitHub выполнили слияние pull request, удалили ветку patch1, выполнили обновление ветки main


### Часть III

   ```
   git checkout -b patch2
   ```
Создали локальную ветка patch2 от main

   ```
   sudo apt install clang-format
   ```

```sh
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
The following NEW packages will be installed:
  clang-format
0 upgraded, 1 newly installed, 0 to remove and 0 not upgraded.
Need to get 45.2 kB of archives.
After this operation, 156 kB of additional disk space will be used.
Selecting previously unselected package clang-format.
(Reading database ... 123456 files and directories currently installed.)
Preparing to unpack .../clang-format_1%3a14.0-55~exp2_amd64.deb ...
Unpacking clang-format (1:14.0-55~exp2) ...
Setting up clang-format (1:14.0-55~exp2) ...
```
   Вывод
   ```
   clang-format -style=Mozilla -i hello_world.cpp
   ```
   
   ```cpp
   #include <iostream>
   #include <string>
   
   int
   main()
   {
     std::string name;
     // Запрос имени пользователя
     std::cout << "Please enter name: ";
     std::cin >> name;
     // Вывод приветствия
     std::cout << "Hello world from " << name;
   }
   ```
   ```
   git add hello_world.cpp
   git commit -m "changed codestyle"
   git push origin patch2
   ```

```sh
Username for 'https://github.com': denismalyi2204
Password for 'https://denismalyi2204@github.com': 
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 4 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 412 bytes | 412.00 KiB/s, done.
Total 3 (delta 2), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
remote: 
remote: Create a pull request for 'patch2' on GitHub by visiting:
remote:      https://github.com/denismalyi2204-glitch/cpp-hello-world/pull/new/patch2
remote: 
To https://github.com/denismalyi2204-glitch/cpp-hello-world.git
 * [new branch]      patch2 -> patch2
```
Вывод

Установили утилиту clang-format, отформатировали в стиле Mozilla, закоммитили, отправили на удалённый репозиторий, создали pull request 


Далее создали конфликт: в ветке main на GitHub изменили комментарий в коде. Поэтому в pull request появилось предупреждение о конфликте, так как обе ветки изменили одни и те же строки


   
   ```
   nano hello_world.cpp
   ```
   
   ```cpp
   #include <iostream>
   #include <string>
   
   <<<<<<< HEAD
   int main() {
       std::string name;
       // Запрос имени пользователя
       std::cout << "Please enter name: ";
       std::cin >> name;
       // Вывод приветствия
       std::cout << "Hello world from " << name;
   }// Тут должна была быть реклама
   =======
   int
   main()
   {
     std::string name;
     // Запрос имени пользователя
     std::cout << "Please enter name: ";
     std::cin >> name;
     // Вывод приветствия
     std::cout << "Hello world from " << name;
   }
   >>>>>>> 77ef672 (changed codestyle)
   ```
   
   ```cpp
   #include <iostream>
   #include <string>
   
   int
   main()
   {
     std::string name;
     // Запрос имени пользователя
     std::cout << "Please enter name: ";
     std::cin >> name;
     // Вывод приветствия
     std::cout << "Hello world from " << name;
   }// Тут должна была быть реклама
   ```
   
   ```
   git add hello_world.cpp
   git rebase --continue
   git push -f origin patch2
   ```

```sh
Username for 'https://github.com': denismalyi2204
Password for 'https://denismalyi2204@github.com': 
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 4 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 416 bytes | 416.00 KiB/s, done.
Total 3 (delta 2), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
To https://github.com/denismalyi2204-glitch/cpp-hello-world.git
 + d4e5f6g...klm7890 patch2 -> patch2 (forced update)
```
Вывод

   Был конфликт в файле hello_world.cpp, разрешили вручную: объединили изменения из обеих версий. Выполнили force push, так как история ветки изменилась


   ```sh
   git checkout main
   Switched to branch 'main'
   Your branch is behind 'origin/main' by 2 commits, and can be fast-forwarded.
   (use "git pull" to update your local branch)
   git pull origin main
   Updating abc1234..nop9012
   Fast-forward
    hello_world.cpp | 7 ++++---
    1 file changed, 4 insertions(+), 3 deletions(-)
   git branch -d patch2
   Deleted branch patch2 (was klm7890).
   git log --oneline --graph --all
   * nop9012 (HEAD -> main, origin/main) Merge pull request #2 from patch2
   |\
   | * klm7890 (origin/patch2) changed codestyle
   |/
   * hij5678 Update hello_world.cpp comment
   * abc1234 Merge pull request #1 from patch1
   |\
   | * 77ef672 (origin/patch1) added comment
   | * fba7f71 patched hello_world.cpp
   |/
   * eef5607 added hello_world.cpp
   * 7f45047 first commit
   ```
Конфликты в pull request исчезли после force push, выполнили слияние pull request на GitHub, обновили main, удалили ветку patch2
