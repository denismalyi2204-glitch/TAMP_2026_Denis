## Laboratory work I

Данная лабораторная работа посвещена изучению утилит для разработки проектов


## Report
```bash
$ export GITHUB_USERNAME=<username>
$ export GIST_TOKEN=<saved_token>
$ alias edit=subl
```
Устанавливаем переменные окружения и псевдоним для edit
```sh
$ mkdir -p ${GITHUB_USERNAME}/workspace
$ cd ${GITHUB_USERNAME}/workspace
$ pwd
```
Создаем директорию, переходим в неё и печатаем адрес
```
/home/ubumba64/denismalyi2204/workspace
```

```sh
$ cd ..
$ pwd
```
Переходим на одну дерикторию выше и выводим ее адрес
```
/home/ubumba64/denismalyi2204
```

```sh
$ mkdir -p workspace/tasks/
$ mkdir -p workspace/projects/
$ mkdir -p workspace/reports/
$ cd workspace
```
Создаем несколько папок и переходим в папку workspace
Будет создана структура директорий:

    workspace/
    ├── tasks/
    ├── projects/
    └── reports/


```sh
# Debian
$ wget https://nodejs.org/dist/v6.11.5/node-v6.11.5-linux-x64.tar.xz
$ tar -xf node-v6.11.5-linux-x64.tar.xz
$ rm -rf node-v6.11.5-linux-x64.tar.xz
$ mv node-v6.11.5-linux-x64 node
```
После выполнения всех команд в текущей директории останется папка node, содержащая распакованную версию Node.js

```sh
$ ls node/bin
$ echo ${PATH}
```
Выводим содержимое папки node/bin и значение переменной окружения PATH 
```sh
$ export PATH=${PATH}:`pwd`/node/bin
$ echo ${PATH}
```
Добавляем в path путь до этой папки чтобы затем мы могли от сюда испольЗовать Node.js и выводим обновленное значение PATH
```sh
$ mkdir scripts
$ cat > scripts/activate<<EOF
export PATH=\${PATH}:`pwd`/node/bin
EOF
$ source scripts/activate
```
создаем папку, далее команда создает файл scripts/activate и записывает в него следующие строки до EOF. 
cat > файл означает «записать ввод в файл» (в данном случае текст будет записан в scripts/activate).
source выполняет команды из файла scripts/activate

```sh
$ gem install gist
```
Устанавливаем Gist

```sh
$ (umask 0077 && echo ${GIST_TOKEN} > ~/.gist)
```
Устанавливаем права записи и записываем в скрытый файл наш токен, так как без него мы не сможем ничего отправлять

```sh
$ export LAB_NUMBER=01
$ git clone https://github.com/tp-labs/lab${LAB_NUMBER} tasks/lab${LAB_NUMBER}
$ mkdir reports/lab${LAB_NUMBER}
$ cp tasks/lab${LAB_NUMBER}/README.md reports/lab${LAB_NUMBER}/REPORT.md
$ cd reports/lab${LAB_NUMBER}
$ edit REPORT.md
$ gist REPORT.md
```
Создаем папку с копией лабораторной работы, редактируем файл с помощью текстового редактора, затем отправляем на GitHub

## Homework
```cpp
$ wget https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz
```
Скачиваем библиотеку _boost_ с помощью утилиты wget.


```sh
$ tar -xf boost_1_69_0.tar.gz -C ~
$ cd ~/boost_1_69_0
```
Разархивируем скаченный файл в директорию ~/boost_1_69_0


```sh
$ find -maxdepth 1 ! -type d  | wc
```
Подсчитаем количество файлов в директории ~/boost_1_69_0, не включая вложенные директории
```sh
     16      16     210
```
Вывод консоли


```sh
$ find ! -type d | wc
```
 Подсчитаем количество файлов в директории ~/boost_1_69_0 включая вложенные директории.
```sh
  62053   62056 3161318
```
Вывод консоли


```sh
$ find ! -type d -name "*.h" | wc
$ find ! -type d -name "*.cpp" | wc
$ find ! -type d ! -name "*.cpp" ! -name "*.h" | wc
```
Подсчитаем количество заголовочных файлов, файлов с расширением cpp, остальные файлы.
```sh
    296     296   11738
  13789   13789  648515
  47968   47971 2501065
```
Вывод консоли

```cpp
$ find -name "any.hpp"
./boost/fusion/include/any.hpp
./boost/fusion/algorithm/query/detail/any.hpp
./boost/fusion/algorithm/query/any.hpp
./boost/proto/detail/any.hpp
./boost/hana/fwd/any.hpp
./boost/hana/any.hpp
./boost/xpressive/detail/utility/any.hpp
./boost/any.hpp
./boost/type_erasure/any.hpp
./boost/spirit/home/support/algorithm/any.hpp
```
Найдём полный пусть до файла any.hpp внутри библиотеки boost.

```sh
$ grep -lr "boost::asio"
```
```
./boost/asio/ts/internet.hpp
./boost/asio/ts/netfwd.hpp
./boost/asio/detail/impl/socket_ops.ipp
./boost/asio/impl/connect.hpp
./boost/asio/impl/read.hpp
./boost/asio/impl/write.hpp
./boost/asio/impl/io_context.ipp
./boost/asio/impl/serial_port_base.ipp
./boost/asio/impl/read_at.hpp
./boost/asio/impl/write_at.hpp
./boost/asio/impl/use_awaitable.hpp
./boost/asio/impl/co_spawn.hpp
./boost/asio/impl/redirect_error.hpp
./boost/asio/impl/awaitable.hpp
./boost/asio/impl/buffered_write_stream.hpp
./boost/asio/impl/buffered_read_stream.hpp
./boost/asio/impl/thread_pool.ipp
./boost/asio/impl/detached.hpp
./boost/asio/impl/use_future.hpp
./boost/asio/impl/post.hpp
./boost/asio/impl/dispatch.hpp
./boost/asio/impl/defer.hpp
./boost/asio/impl/executor.hpp
./boost/asio/impl/execution_context.ipp
./boost/asio/impl/system_context.ipp
./boost/asio/impl/system_executor.hpp
./boost/asio/impl/error.ipp
./boost/asio/ssl/impl/rfc2818_verification.ipp
./boost/asio/ssl/impl/context.ipp
./boost/asio/ssl/impl/error.ipp
./boost/asio/ssl/detail/impl/engine.ipp
./boost/asio/ssl/detail/impl/openssl_init.ipp
./boost/asio/spawn.hpp
./boost/asio/connect.hpp
./boost/asio/write.hpp
./boost/asio/read.hpp
./boost/asio/read_at.hpp
./boost/asio/write_at.hpp
./boost/asio/co_spawn.hpp
./boost/asio/redirect_error.hpp
./boost/asio/use_awaitable.hpp
./boost/asio/awaitable.hpp
./boost/asio/use_future.hpp
./boost/asio/detached.hpp
./boost/boost/asio.hpp
./boost/asio/ts/buffer.hpp
./boost/asio/ts/executor.hpp
./boost/asio/ts/socket.hpp
./boost/asio/ts/timer.hpp
```
Выведем в консоль все файлы, где упоминается последовательность boost::asio.

```sh
$ ./bootstrap.sh
$ sudo ./b2 install
```
```
Building Boost.Build engine with toolset gcc... 
Detecting Python version... 3.7
Detecting Python root... /usr
Unicode/ICU support for Boost.Regex? not found.
Backing up existing Boost.Build configuration in project-config.jam.bak
Generating Boost.Build configuration in project-config.jam...

Bootstrapping is done. To build, run:

    ./b2
    
To adjust configuration, edit 'project-config.jam'.
Further information:

   - Command line help:
     ./b2 --help
     
   - Getting started guide: 
     http://www.boost.org/more/getting_started/unix-variants.html
     
   - Boost.Build documentation:
     http://www.boost.org/build/
```
```
...patience...
...patience...
...found 18975 targets...
...updating 3877 targets...
gcc.compile.c++ bin.v2/libs/thread/build/gcc-8/release/threading-multi/pthread/thread.o
gcc.compile.c++ bin.v2/libs/thread/build/gcc-8/release/threading-multi/pthread/once.o
gcc.link.dll bin.v2/libs/thread/build/gcc-8/release/threading-multi/libboost_thread.so.1.69.0
gcc.link.dll ../../stage/lib/libboost_thread.so.1.69.0
gcc.compile.c++ bin.v2/libs/chrono/build/gcc-8/release/threading-multi/chrono.o
gcc.compile.c++ bin.v2/libs/chrono/build/gcc-8/release/threading-multi/process_cpu_clocks.o
gcc.compile.c++ bin.v2/libs/chrono/build/gcc-8/release/threading-multi/thread_clock.o
gcc.link.dll bin.v2/libs/chrono/build/gcc-8/release/threading-multi/libboost_chrono.so.1.69.0
gcc.link.dll ../../stage/lib/libboost_chrono.so.1.69.0
gcc.compile.c++ bin.v2/libs/date_time/build/gcc-8/release/threading-multi/gregorian/greg_month.o
gcc.compile.c++ bin.v2/libs/date_time/build/gcc-8/release/threading-multi/gregorian/greg_weekday.o
gcc.compile.c++ bin.v2/libs/date_time/build/gcc-8/release/threading-multi/gregorian/date_generators.o
gcc.link.dll bin.v2/libs/date_time/build/gcc-8/release/threading-multi/libboost_date_time.so.1.69.0
gcc.link.dll ../../stage/lib/libboost_date_time.so.1.69.0
...updated 3877 targets...
...updated 2455 targets...

The following directory should be added to compiler include paths:
    /usr/local/include

The following directory should be added to linker library paths:
    /usr/local/lib
```

Скомпилируем boost

```sh
$ mkdir ~/boost-libs
$ cp `find -name "*.a"` ~/boost-libs
```
Переносим все скомпилированные ранее статические библиотеки в директорию ~/boost-libs.

```sh
$ cd ~/boost-libs
$ find ! -type d -exec du -h {} +
```
Подсчитаем сколько занимает дискового пространства каждый файл в этой директории.
```cpp
544K	./libboost_math_c99.a
172K	./libboost_iostreams.a
24K	./libboost_stacktrace_addr2line.a
1.2M	./libboost_serialization.a
2.7M	./libboost_regex.a
4.0K	./libboost_exception.a
212K	./libboost_prg_exec_monitor.a
2.3M	./libboost_test_exec_monitor.a
152K	./libboost_date_time.a
232K	./libboost_fiber.a
4.5M	./libboost_wave.a
16K	./libboost_stacktrace_basic.a
56K	./libboost_timer.a
848K	./libboost_graph.a
80K	./libboost_random.a
332K	./libboost_contract.a
2.7M	./libboost_math_tr1.a
4.0K	./libboost_atomic.a
20K	./libboost_stacktrace_backtrace.a
1.6M	./libboost_program_options.a
464K	./libboost_math_c99l.a
4.0K	./libboost_stacktrace_noop.a
148K	./libboost_container.a
4.0K	./libboost_system.a
24K	./libboost_context.a
416K	./libboost_filesystem.a
796K	./libboost_wserialization.a
2.7M	./libboost_math_tr1l.a
2.0M	./libboost_locale.a
2.6M	./libboost_math_tr1f.a
236K	./libboost_chrono.a
448K	./libboost_math_c99f.a
2.3M	./libboost_unit_test_framework.a
```
Вывод консоли

```sh
$ find ! -type d -exec du {} + | sort -rn | head -n 10
```
Находим 10 самых "тяжёлых" файлов.
```cpp
10
4588	./libboost_wave.a
2756	./libboost_regex.a
2732	./libboost_math_tr1.a
2700	./libboost_math_tr1l.a
2648	./libboost_math_tr1f.a
2308	./libboost_test_exec_monitor.a
2288	./libboost_unit_test_framework.a
2044	./libboost_locale.a
1576	./libboost_program_options.a
1200	./libboost_serialization.a
```
Вывод консоли
