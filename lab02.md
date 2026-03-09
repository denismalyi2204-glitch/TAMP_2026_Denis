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
Привязываем удаленный репозиторий к локальному с именем origin и совмещаем их

```sh
$ touch README.md
$ git status
$ git add README.md
$ git commit -m"added README.md"
$ git push origin master
```
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
   
   ```
   git add hello_world.cpp
   git commit -m "added hello_world.cpp"
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
В ветке `patch1` добавили комментарии к коду, закоммитили изменения, выполнили push в удалённую ветку


   ```
   git checkout main
   git pull origin main
   git branch -d patch1
   ```
На GitHub выполнили слияние pull request, удалили ветку patch1, выполнили обновление ветки main


### Часть III

   ```
   git checkout -b patch2
   ```
Создали локальную ветка patch2 от main

   ```
   sudo apt install clang-format
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
   Был конфликт в файле hello_world.cpp, разрешили вручную: объединили изменения из обеих версий. Выполнили force push, так как история ветки изменилась


   ```
   git checkout main
   git pull origin main
   git branch -d patch2
   git log --oneline --graph --all
   ```
Конфликты в pull request исчезли после force push, выполнили слияние pull request на GitHub, обновили main, удалили ветку patch2


