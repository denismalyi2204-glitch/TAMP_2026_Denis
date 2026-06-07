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
Fetching gist-6.0.0.gem
Successfully installed gist-6.0.0
Parsing documentation for gist-6.0.0
Installing ri documentation for gist-6.0.0
Done installing documentation for gist after 0 seconds
1 gem installed
```

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
--2026-06-07 17:45:40--  https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz
Resolving sourceforge.net (sourceforge.net)... 104.18.13.149, 104.18.12.149, 2606:4700::6812:d95, ...
Connecting to sourceforge.net (sourceforge.net)|104.18.13.149|:443... connected.
HTTP request sent, awaiting response... 301 Moved Permanently
Location: https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz/ [following]
--2026-06-07 17:45:40--  https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz/
Reusing existing connection to sourceforge.net:443.
HTTP request sent, awaiting response... 301 Moved Permanently
Location: https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz/download [following]
--2026-06-07 17:45:41--  https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz/download
Reusing existing connection to sourceforge.net:443.
HTTP request sent, awaiting response... 302 Found
Location: https://downloads.sourceforge.net/project/boost/boost/1.69.0/boost_1_69_0.tar.gz?ts=gAAAAABqJa5b4ezWsAcnS-zuTBa_BJcBgiAAeR9XDiqb8oLpIqM8Jlf1VMMRWkma9I8QLicSD5KZqkjll58y1mQoUIzulT0vLQ%3D%3D&use_mirror=sf-eu-introserv-2&r= [following]
--2026-06-07 17:45:41--  https://downloads.sourceforge.net/project/boost/boost/1.69.0/boost_1_69_0.tar.gz?ts=gAAAAABqJa5b4ezWsAcnS-zuTBa_BJcBgiAAeR9XDiqb8oLpIqM8Jlf1VMMRWkma9I8QLicSD5KZqkjll58y1mQoUIzulT0vLQ%3D%3D&use_mirror=sf-eu-introserv-2&r=
Resolving downloads.sourceforge.net (downloads.sourceforge.net)... 104.18.12.149, 104.18.13.149, 2606:4700::6812:d95, ...
Connecting to downloads.sourceforge.net (downloads.sourceforge.net)|104.18.12.149|:443... connected.
HTTP request sent, awaiting response... 302 Found
Location: https://sf-eu-introserv-2.dl.sourceforge.net/project/boost/boost/1.69.0/boost_1_69_0.tar.gz?viasf=1&fid=0b04351a8c20a7ca [following]
--2026-06-07 17:45:41--  https://sf-eu-introserv-2.dl.sourceforge.net/project/boost/boost/1.69.0/boost_1_69_0.tar.gz?viasf=1&fid=0b04351a8c20a7ca
Resolving sf-eu-introserv-2.dl.sourceforge.net (sf-eu-introserv-2.dl.sourceforge.net)... 51.91.221.175
Connecting to sf-eu-introserv-2.dl.sourceforge.net (sf-eu-introserv-2.dl.sourceforge.net)|51.91.221.175|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 111710205 (107M) [application/x-gzip]
Saving to: ‘boost_1_69_0.tar.gz’

boost_1_69_0.tar.gz 100%[===================>] 106.53M  2.22MB/s    in 61s     

2026-06-07 17:46:42 (1.75 MB/s) - ‘boost_1_69_0.tar.gz’ saved [111710205/111710205]
```


```sh
$ tar -xf boost_1_69_0.tar.gz -C ~
ls -ld ~/boost_1_69_0
$ cd ~/boost_1_69_0
```
Разархивируем скаченный файл в директорию ~/boost_1_69_0
```sh
drwxrwxr-x 9 ubumba64 ubumba64 4096 Dec  5  2018 /home/ubumba64/boost_1
```

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
./boost/proto/detail/any.hpp
./boost/spirit/home/support/algorithm/any.hpp
./boost/type_erasure/any.hpp
./boost/xpressive/detail/utility/any.hpp
./boost/fusion/algorithm/query/detail/any.hpp
./boost/fusion/algorithm/query/any.hpp
./boost/fusion/include/any.hpp
./boost/any.hpp
./boost/hana/fwd/any.hpp
./boost/hana/any.hpp
```
Найдём полный пусть до файла any.hpp внутри библиотеки boost.

```sh
$ grep -lr "boost::asio"
```
```
libs/process/example/wait.cpp
libs/process/example/async_io.cpp
libs/process/example/io.cpp
libs/process/doc/extend.qbk
libs/process/doc/tutorial.qbk
libs/process/doc/autodoc.xml
libs/process/test/exit_code.cpp
libs/process/test/async_fut.cpp
libs/process/test/async_system_stackful_error.cpp
libs/process/test/on_exit3.cpp
libs/process/test/spawn_fail.cpp
libs/process/test/wait.cpp
libs/process/test/system_test1.cpp
libs/process/test/bind_stderr.cpp
libs/process/test/async_system_stackful.cpp
libs/process/test/on_exit2.cpp
libs/process/test/system_test2.cpp
libs/process/test/bind_stdin.cpp
libs/process/test/async_system_stackful_except.cpp
libs/process/test/async_system_fail.cpp
libs/process/test/bind_stdout_stderr.cpp
libs/process/test/async.cpp
libs/process/test/async_system_stackless.cpp
libs/process/test/bind_stdout.cpp
libs/process/test/async_system_future.cpp
libs/process/test/on_exit.cpp
libs/process/test/async_pipe.cpp
libs/process/test/spawn.cpp
libs/log/doc/tmp/sinks_reference.xml
libs/log/src/syslog_backend.cpp
libs/phoenix/example/adapted_echo_server.cpp
libs/coroutine2/doc/coro.qbk
libs/coroutine2/doc/motivation.qbk
libs/thread/test/test_9303.cpp
libs/beast/example/doc/http_examples.hpp
libs/beast/example/websocket/server/stackless/websocket_server_stackless.cpp
libs/beast/example/websocket/server/coro-ssl/websocket_server_coro_ssl.cpp
libs/beast/example/websocket/server/sync/websocket_server_sync.cpp
libs/beast/example/websocket/server/coro/websocket_server_coro.cpp
libs/beast/example/websocket/server/fast/websocket_server_fast.cpp
libs/beast/example/websocket/server/stackless-ssl/websocket_server_stackless_ssl.cpp
libs/beast/example/websocket/server/async-ssl/websocket_server_async_ssl.cpp
libs/beast/example/websocket/server/sync-ssl/websocket_server_sync_ssl.cpp
libs/beast/example/websocket/server/async/websocket_server_async.cpp
libs/beast/example/websocket/client/coro-ssl/websocket_client_coro_ssl.cpp
libs/beast/example/websocket/client/sync/websocket_client_sync.cpp
libs/beast/example/websocket/client/coro/websocket_client_coro.cpp
libs/beast/example/websocket/client/async-ssl/websocket_client_async_ssl.cpp
libs/beast/example/websocket/client/sync-ssl/websocket_client_sync_ssl.cpp
libs/beast/example/websocket/client/async/websocket_client_async.cpp
libs/beast/example/cppcon2018/net.hpp
libs/beast/example/echo-op/echo_op.cpp
libs/beast/example/http/server/stackless/http_server_stackless.cpp
libs/beast/example/http/server/coro-ssl/http_server_coro_ssl.cpp
libs/beast/example/http/server/small/http_server_small.cpp
libs/beast/example/http/server/sync/http_server_sync.cpp
libs/beast/example/http/server/coro/http_server_coro.cpp
libs/beast/example/http/server/fast/http_server_fast.cpp
libs/beast/example/http/server/flex/http_server_flex.cpp
libs/beast/example/http/server/stackless-ssl/http_server_stackless_ssl.cpp
libs/beast/example/http/server/async-ssl/http_server_async_ssl.cpp
libs/beast/example/http/server/sync-ssl/http_server_sync_ssl.cpp
libs/beast/example/http/server/async/http_server_async.cpp
libs/beast/example/http/client/coro-ssl/http_client_coro_ssl.cpp
libs/beast/example/http/client/sync/http_client_sync.cpp
libs/beast/example/http/client/coro/http_client_coro.cpp
libs/beast/example/http/client/crawl/http_crawl.cpp
libs/beast/example/http/client/async-ssl/http_client_async_ssl.cpp
libs/beast/example/http/client/sync-ssl/http_client_sync_ssl.cpp
libs/beast/example/http/client/async/http_client_async.cpp
libs/beast/example/common/detect_ssl.hpp
libs/beast/example/common/root_certificates.hpp
libs/beast/example/common/server_certificate.hpp
libs/beast/example/common/session_alloc.hpp
libs/beast/example/advanced/server/advanced_server.cpp
libs/beast/example/advanced/server-flex/advanced_server_flex.cpp
libs/beast/CHANGELOG.md
libs/beast/doc/qbk/reference.qbk
libs/beast/doc/qbk/00_main.qbk
libs/beast/doc/qbk/07_concepts/DynamicBuffer.qbk
libs/beast/doc/qbk/07_concepts/Streams.qbk
libs/beast/doc/qbk/03_core/1_asio.qbk
libs/beast/doc/qbk/08_design/3_websocket_zaphoyd.qbk
libs/beast/doc/qbk/08_design/4_faq.qbk
libs/beast/doc/docca/include/docca/doxygen.xsl
libs/beast/doc/html/beast/more_examples/expect_100_continue_server.html
libs/beast/doc/html/beast/ref/boost__beast__websocket__async_teardown/overload2.html
libs/beast/doc/html/beast/ref/boost__beast__websocket__async_teardown/overload1.html
libs/beast/doc/html/beast/ref/boost__beast__websocket__async_teardown/overload3.html
libs/beast/doc/html/beast/ref/boost__beast__basic_timeout_socket/async_read_some.html
libs/beast/doc/html/beast/ref/boost__beast__basic_timeout_socket/async_write_some.html
libs/beast/doc/html/beast/ref/boost__beast__http__error.html
libs/beast/doc/html/beast/using_io/writing_composed_operations.html
libs/beast/doc/html/beast/using_io/example_detect_ssl.html
libs/beast/test/doc/http_examples.cpp
libs/beast/test/doc/http_snippets.cpp
libs/beast/test/doc/core_snippets.cpp
libs/beast/test/doc/websocket_snippets.cpp
libs/beast/test/doc/exemplars.cpp
libs/beast/test/doc/core_examples.cpp
libs/beast/test/beast/core/buffer_test.hpp
libs/beast/test/beast/core/multi_buffer.cpp
libs/beast/test/beast/core/bind_handler.cpp
libs/beast/test/beast/core/flat_static_buffer.cpp
libs/beast/test/beast/core/buffers_cat.cpp
libs/beast/test/beast/core/static_buffer.cpp
libs/beast/test/beast/core/flat_buffer.cpp
libs/beast/test/beast/core/buffers_prefix.cpp
libs/beast/test/beast/core/buffer.cpp
libs/beast/test/beast/core/buffers_suffix.cpp
libs/beast/test/beast/core/read_size.cpp
libs/beast/test/beast/core/type_traits.cpp
libs/beast/test/beast/core/buffers_adapter.cpp
libs/beast/test/beast/core/buffered_read_stream.cpp
libs/beast/test/beast/websocket/read1.cpp
libs/beast/test/beast/websocket/accept.cpp
libs/beast/test/beast/websocket/close.cpp
libs/beast/test/beast/websocket/test.hpp
libs/beast/test/beast/websocket/read2.cpp
libs/beast/test/beast/websocket/stream.cpp
libs/beast/test/beast/websocket/utf8_checker.cpp
libs/beast/test/beast/websocket/handshake.cpp
libs/beast/test/beast/websocket/ping.cpp
libs/beast/test/beast/websocket/write.cpp
libs/beast/test/beast/websocket/doc_snippets.cpp
libs/beast/test/beast/experimental/timeout_service.cpp
libs/beast/test/beast/experimental/timeout_socket.cpp
libs/beast/test/beast/experimental/icy_stream.cpp
libs/beast/test/beast/experimental/flat_stream.cpp
libs/beast/test/beast/http/read.cpp
libs/beast/test/beast/http/message_fuzz.hpp
libs/beast/test/beast/http/chunk_encode.cpp
libs/beast/test/beast/http/dynamic_body.cpp
libs/beast/test/beast/http/test_parser.hpp
libs/beast/test/beast/http/basic_parser.cpp
libs/beast/test/beast/http/span_body.cpp
libs/beast/test/beast/http/serializer.cpp
libs/beast/test/beast/http/write.cpp
libs/beast/test/beast/http/parser.cpp
libs/beast/test/beast/http/file_body.cpp
libs/beast/test/bench/wsload/wsload.cpp
libs/beast/test/bench/buffers/bench_buffers.cpp
libs/beast/test/bench/parser/nodejs_parser.hpp
libs/beast/test/bench/parser/bench_parser.cpp
libs/beast/test/extras/include/boost/beast/test/websocket.hpp
libs/beast/test/extras/include/boost/beast/test/yield_to.hpp
libs/beast/test/extras/include/boost/beast/test/sig_wait.hpp
libs/asio/example/cpp17/coroutines_ts/chat_server.cpp
libs/asio/example/cpp17/coroutines_ts/refactored_echo_server.cpp
libs/asio/example/cpp17/coroutines_ts/echo_server.cpp
libs/asio/example/cpp17/coroutines_ts/double_buffered_echo_server.cpp
libs/asio/example/cpp17/coroutines_ts/range_based_for.cpp
libs/asio/example/cpp03/timers/time_t_timer.cpp
libs/asio/example/cpp03/spawn/parallel_grep.cpp
libs/asio/example/cpp03/spawn/echo_server.cpp
libs/asio/example/cpp03/chat/chat_server.cpp
libs/asio/example/cpp03/chat/chat_client.cpp
libs/asio/example/cpp03/chat/posix_chat_client.cpp
libs/asio/example/cpp03/ssl/client.cpp
libs/asio/example/cpp03/ssl/server.cpp
libs/asio/example/cpp03/buffers/reference_counted.cpp
libs/asio/example/cpp03/services/basic_logger.hpp
libs/asio/example/cpp03/services/logger_service.hpp
libs/asio/example/cpp03/services/daytime_client.cpp
libs/asio/example/cpp03/services/logger_service.cpp
libs/asio/example/cpp03/multicast/sender.cpp
libs/asio/example/cpp03/multicast/receiver.cpp
libs/asio/example/cpp03/timeouts/blocking_tcp_client.cpp
libs/asio/example/cpp03/timeouts/blocking_token_tcp_client.cpp
libs/asio/example/cpp03/timeouts/async_tcp_client.cpp
libs/asio/example/cpp03/timeouts/server.cpp
libs/asio/example/cpp03/timeouts/blocking_udp_client.cpp
libs/asio/example/cpp03/nonblocking/third_party_lib.cpp
libs/asio/example/cpp03/socks4/socks4.hpp
libs/asio/example/cpp03/socks4/sync_client.cpp
libs/asio/example/cpp03/icmp/ipv4_header.hpp
libs/asio/example/cpp03/icmp/ping.cpp
libs/asio/example/cpp03/echo/blocking_tcp_echo_server.cpp
libs/asio/example/cpp03/echo/blocking_tcp_echo_client.cpp
libs/asio/example/cpp03/echo/blocking_udp_echo_server.cpp
libs/asio/example/cpp03/echo/blocking_udp_echo_client.cpp
libs/asio/example/cpp03/echo/async_tcp_echo_server.cpp
libs/asio/example/cpp03/echo/async_udp_echo_server.cpp
libs/asio/example/cpp03/allocation/server.cpp
libs/asio/example/cpp03/fork/daemon.cpp
libs/asio/example/cpp03/fork/process_per_connection.cpp
libs/asio/example/cpp03/tutorial/timer5/timer.cpp
libs/asio/example/cpp03/tutorial/daytime3/server.cpp
libs/asio/example/cpp03/tutorial/daytime1/client.cpp
libs/asio/example/cpp03/tutorial/daytime_dox.txt
libs/asio/example/cpp03/tutorial/daytime4/client.cpp
libs/asio/example/cpp03/tutorial/timer2/timer.cpp
libs/asio/example/cpp03/tutorial/daytime7/server.cpp
libs/asio/example/cpp03/tutorial/daytime6/server.cpp
libs/asio/example/cpp03/tutorial/daytime5/server.cpp
libs/asio/example/cpp03/tutorial/timer4/timer.cpp
libs/asio/example/cpp03/tutorial/timer1/timer.cpp
libs/asio/example/cpp03/tutorial/timer3/timer.cpp
libs/asio/example/cpp03/tutorial/daytime2/server.cpp
libs/asio/example/cpp03/tutorial/timer_dox.txt
libs/asio/example/cpp03/http/server/reply.cpp
libs/asio/example/cpp03/http/server/connection.hpp
libs/asio/example/cpp03/http/server/connection.cpp
libs/asio/example/cpp03/http/server/reply.hpp
libs/asio/example/cpp03/http/server/server.hpp
libs/asio/example/cpp03/http/server/server.cpp
libs/asio/example/cpp03/http/client/sync_client.cpp
libs/asio/example/cpp03/http/client/async_client.cpp
libs/asio/example/cpp03/http/server4/reply.cpp
libs/asio/example/cpp03/http/server4/reply.hpp
libs/asio/example/cpp03/http/server4/server.hpp
libs/asio/example/cpp03/http/server4/request_parser.hpp
libs/asio/example/cpp03/http/server4/main.cpp
libs/asio/example/cpp03/http/server4/server.cpp
libs/asio/example/cpp03/http/server2/reply.cpp
libs/asio/example/cpp03/http/server2/connection.hpp
libs/asio/example/cpp03/http/server2/connection.cpp
libs/asio/example/cpp03/http/server2/io_context_pool.hpp
libs/asio/example/cpp03/http/server2/reply.hpp
libs/asio/example/cpp03/http/server2/server.hpp
libs/asio/example/cpp03/http/server2/io_context_pool.cpp
libs/asio/example/cpp03/http/server2/server.cpp
libs/asio/example/cpp03/http/server3/reply.cpp
libs/asio/example/cpp03/http/server3/connection.hpp
libs/asio/example/cpp03/http/server3/connection.cpp
libs/asio/example/cpp03/http/server3/reply.hpp
libs/asio/example/cpp03/http/server3/server.hpp
libs/asio/example/cpp03/http/server3/server.cpp
libs/asio/example/cpp03/windows/transmit_file.cpp
libs/asio/example/cpp03/iostreams/daytime_client.cpp
libs/asio/example/cpp03/iostreams/http_client.cpp
libs/asio/example/cpp03/iostreams/daytime_server.cpp
libs/asio/example/cpp03/local/stream_client.cpp
libs/asio/example/cpp03/local/iostream_client.cpp
libs/asio/example/cpp03/local/stream_server.cpp
libs/asio/example/cpp03/local/connect_pair.cpp
libs/asio/example/cpp03/serialization/connection.hpp
libs/asio/example/cpp03/serialization/client.cpp
libs/asio/example/cpp03/serialization/server.cpp
libs/asio/example/cpp03/invocation/prioritised_handlers.cpp
libs/asio/example/cpp03/porthopper/client.cpp
libs/asio/example/cpp03/porthopper/protocol.hpp
libs/asio/example/cpp03/porthopper/server.cpp
libs/asio/example/cpp11/timers/time_t_timer.cpp
libs/asio/example/cpp11/handler_tracking/custom_tracking.hpp
libs/asio/example/cpp11/handler_tracking/async_tcp_echo_server.cpp
libs/asio/example/cpp11/spawn/parallel_grep.cpp
libs/asio/example/cpp11/spawn/echo_server.cpp
libs/asio/example/cpp11/chat/chat_server.cpp
libs/asio/example/cpp11/chat/chat_client.cpp
libs/asio/example/cpp11/ssl/client.cpp
libs/asio/example/cpp11/ssl/server.cpp
libs/asio/example/cpp11/buffers/reference_counted.cpp
libs/asio/example/cpp11/multicast/sender.cpp
libs/asio/example/cpp11/multicast/receiver.cpp
libs/asio/example/cpp11/timeouts/blocking_tcp_client.cpp
libs/asio/example/cpp11/timeouts/blocking_token_tcp_client.cpp
libs/asio/example/cpp11/timeouts/async_tcp_client.cpp
libs/asio/example/cpp11/timeouts/server.cpp
libs/asio/example/cpp11/timeouts/blocking_udp_client.cpp
libs/asio/example/cpp11/nonblocking/third_party_lib.cpp
libs/asio/example/cpp11/socks4/socks4.hpp
libs/asio/example/cpp11/socks4/sync_client.cpp
libs/asio/example/cpp11/executors/actor.cpp
libs/asio/example/cpp11/executors/priority_scheduler.cpp
libs/asio/example/cpp11/executors/bank_account_2.cpp
libs/asio/example/cpp11/executors/bank_account_1.cpp
libs/asio/example/cpp11/executors/fork_join.cpp
libs/asio/example/cpp11/executors/pipeline.cpp
libs/asio/example/cpp11/operations/composed_4.cpp
libs/asio/example/cpp11/operations/composed_5.cpp
libs/asio/example/cpp11/operations/composed_1.cpp
libs/asio/example/cpp11/operations/composed_2.cpp
libs/asio/example/cpp11/operations/composed_3.cpp
libs/asio/example/cpp11/echo/blocking_tcp_echo_server.cpp
libs/asio/example/cpp11/echo/blocking_tcp_echo_client.cpp
libs/asio/example/cpp11/echo/blocking_udp_echo_server.cpp
libs/asio/example/cpp11/echo/blocking_udp_echo_client.cpp
libs/asio/example/cpp11/echo/async_tcp_echo_server.cpp
libs/asio/example/cpp11/echo/async_udp_echo_server.cpp
libs/asio/example/cpp11/allocation/server.cpp
libs/asio/example/cpp11/fork/daemon.cpp
libs/asio/example/cpp11/fork/process_per_connection.cpp
libs/asio/example/cpp11/http/server/reply.cpp
libs/asio/example/cpp11/http/server/connection.hpp
libs/asio/example/cpp11/http/server/connection.cpp
libs/asio/example/cpp11/http/server/reply.hpp
libs/asio/example/cpp11/http/server/server.hpp
libs/asio/example/cpp11/http/server/server.cpp
libs/asio/example/cpp11/futures/daytime_client.cpp
libs/asio/example/cpp11/iostreams/http_client.cpp
libs/asio/example/cpp11/local/stream_client.cpp
libs/asio/example/cpp11/local/iostream_client.cpp
libs/asio/example/cpp11/local/stream_server.cpp
libs/asio/example/cpp11/local/connect_pair.cpp
libs/asio/example/cpp11/invocation/prioritised_handlers.cpp
libs/asio/doc/reference.qbk
libs/asio/doc/overview/cpp2011.qbk
libs/asio/doc/overview/protocols.qbk
libs/asio/doc/overview/other_protocols.qbk
libs/asio/doc/overview/allocation.qbk
libs/asio/doc/overview/spawn.qbk
libs/asio/doc/overview/signals.qbk
libs/asio/doc/overview/buffers.qbk
libs/asio/doc/overview/coroutines_ts.qbk
libs/asio/doc/overview/line_based.qbk
libs/asio/doc/overview/ssl.qbk
libs/asio/doc/overview/coroutine.qbk
libs/asio/doc/overview/basics.qbk
libs/asio/doc/overview/posix.qbk
libs/asio/doc/overview/strands.qbk
libs/asio/doc/using.qbk
libs/asio/doc/examples.qbk
libs/asio/doc/tutorial.qbk
libs/asio/doc/requirements/ConstBufferSequence.qbk
libs/asio/doc/requirements/ReadHandler.qbk
libs/asio/doc/requirements/BufferedHandshakeHandler.qbk
libs/asio/doc/requirements/AcceptHandler.qbk
libs/asio/doc/requirements/ResolveHandler.qbk
libs/asio/doc/requirements/SignalHandler.qbk
libs/asio/doc/requirements/ConnectHandler.qbk
libs/asio/doc/requirements/Handler.qbk
libs/asio/doc/requirements/MoveAcceptHandler.qbk
libs/asio/doc/requirements/MutableBufferSequence.qbk
libs/asio/doc/requirements/RangeConnectHandler.qbk
libs/asio/doc/requirements/WaitHandler.qbk
libs/asio/doc/requirements/IteratorConnectHandler.qbk
libs/asio/doc/requirements/ShutdownHandler.qbk
libs/asio/doc/requirements/HandshakeHandler.qbk
libs/asio/doc/requirements/WriteHandler.qbk
libs/asio/doc/reference.xsl
libs/asio/test/read.cpp
libs/asio/test/read_until.cpp
libs/asio/test/buffered_stream.cpp
libs/asio/test/io_context.cpp
libs/asio/test/coroutine.cpp
libs/asio/test/system_timer.cpp
libs/asio/test/unit_test.hpp
libs/asio/test/ssl/stream.cpp
libs/asio/test/read_at.cpp
libs/asio/test/streambuf.cpp
libs/asio/test/connect.cpp
libs/asio/test/buffers_iterator.cpp
libs/asio/test/is_read_buffered.cpp
libs/asio/test/write_at.cpp
libs/asio/test/serial_port.cpp
libs/asio/test/buffered_write_stream.cpp
libs/asio/test/deadline_timer.cpp
libs/asio/test/use_future.cpp
libs/asio/test/socket_base.cpp
libs/asio/test/archetypes/async_ops.hpp
libs/asio/test/archetypes/deprecated_async_ops.hpp
libs/asio/test/strand.cpp
libs/asio/test/posix/stream_descriptor.cpp
libs/asio/test/buffer.cpp
libs/asio/test/windows/stream_handle.cpp
libs/asio/test/windows/overlapped_ptr.cpp
libs/asio/test/windows/object_handle.cpp
libs/asio/test/windows/random_access_handle.cpp
libs/asio/test/local/datagram_protocol.cpp
libs/asio/test/local/stream_protocol.cpp
libs/asio/test/local/connect_pair.cpp
libs/asio/test/ip/network_v6.cpp
libs/asio/test/ip/tcp.cpp
libs/asio/test/ip/network_v4.cpp
libs/asio/test/ip/icmp.cpp
libs/asio/test/ip/unicast.cpp
libs/asio/test/ip/address_v4.cpp
libs/asio/test/ip/udp.cpp
libs/asio/test/ip/address.cpp
libs/asio/test/ip/host_name.cpp
libs/asio/test/ip/multicast.cpp
libs/asio/test/ip/v6_only.cpp
libs/asio/test/ip/address_v6.cpp
libs/asio/test/serial_port_base.cpp
libs/asio/test/error.cpp
libs/asio/test/write.cpp
libs/asio/test/signal_set.cpp
libs/asio/test/latency/udp_server.cpp
libs/asio/test/latency/udp_client.cpp
libs/asio/test/latency/tcp_server.cpp
libs/asio/test/latency/tcp_client.cpp
libs/asio/test/is_write_buffered.cpp
libs/asio/test/generic/datagram_protocol.cpp
libs/asio/test/generic/raw_protocol.cpp
libs/asio/test/generic/stream_protocol.cpp
libs/asio/test/generic/seq_packet_protocol.cpp
libs/asio/test/buffered_read_stream.cpp
libs/fiber/doc/fibers.qbk
libs/fiber/doc/integration.qbk
libs/fiber/doc/callbacks.qbk
libs/fiber/doc/asio.qbk
libs/fiber/examples/asio/autoecho.cpp
libs/fiber/examples/asio/ps/subscriber.cpp
libs/fiber/examples/asio/ps/publisher.cpp
libs/fiber/examples/asio/ps/server.cpp
libs/fiber/examples/asio/exchange.cpp
libs/fiber/examples/asio/round_robin.hpp
libs/coroutine/doc/coro.qbk
libs/coroutine/doc/motivation.qbk
libs/coroutine/doc/html/coroutine/motivation.html
doc/html/boost_asio/example/cpp17/coroutines_ts/chat_server.cpp
doc/html/boost_asio/example/cpp17/coroutines_ts/refactored_echo_server.cpp
doc/html/boost_asio/example/cpp17/coroutines_ts/echo_server.cpp
doc/html/boost_asio/example/cpp17/coroutines_ts/double_buffered_echo_server.cpp
doc/html/boost_asio/example/cpp17/coroutines_ts/range_based_for.cpp
doc/html/boost_asio/example/cpp03/timers/time_t_timer.cpp
doc/html/boost_asio/example/cpp03/spawn/parallel_grep.cpp
doc/html/boost_asio/example/cpp03/spawn/echo_server.cpp
doc/html/boost_asio/example/cpp03/chat/chat_server.cpp
doc/html/boost_asio/example/cpp03/chat/chat_client.cpp
doc/html/boost_asio/example/cpp03/chat/posix_chat_client.cpp
doc/html/boost_asio/example/cpp03/ssl/client.cpp
doc/html/boost_asio/example/cpp03/ssl/server.cpp
doc/html/boost_asio/example/cpp03/buffers/reference_counted.cpp
doc/html/boost_asio/example/cpp03/services/basic_logger.hpp
doc/html/boost_asio/example/cpp03/services/logger_service.hpp
doc/html/boost_asio/example/cpp03/services/daytime_client.cpp
doc/html/boost_asio/example/cpp03/services/logger_service.cpp
doc/html/boost_asio/example/cpp03/multicast/sender.cpp
doc/html/boost_asio/example/cpp03/multicast/receiver.cpp
doc/html/boost_asio/example/cpp03/timeouts/blocking_tcp_client.cpp
doc/html/boost_asio/example/cpp03/timeouts/blocking_token_tcp_client.cpp
doc/html/boost_asio/example/cpp03/timeouts/async_tcp_client.cpp
doc/html/boost_asio/example/cpp03/timeouts/server.cpp
doc/html/boost_asio/example/cpp03/timeouts/blocking_udp_client.cpp
doc/html/boost_asio/example/cpp03/nonblocking/third_party_lib.cpp
doc/html/boost_asio/example/cpp03/socks4/socks4.hpp
doc/html/boost_asio/example/cpp03/socks4/sync_client.cpp
doc/html/boost_asio/example/cpp03/icmp/ipv4_header.hpp
doc/html/boost_asio/example/cpp03/icmp/ping.cpp
doc/html/boost_asio/example/cpp03/echo/blocking_tcp_echo_server.cpp
doc/html/boost_asio/example/cpp03/echo/blocking_tcp_echo_client.cpp
doc/html/boost_asio/example/cpp03/echo/blocking_udp_echo_server.cpp
doc/html/boost_asio/example/cpp03/echo/blocking_udp_echo_client.cpp
doc/html/boost_asio/example/cpp03/echo/async_tcp_echo_server.cpp
doc/html/boost_asio/example/cpp03/echo/async_udp_echo_server.cpp
doc/html/boost_asio/example/cpp03/allocation/server.cpp
doc/html/boost_asio/example/cpp03/fork/daemon.cpp
doc/html/boost_asio/example/cpp03/fork/process_per_connection.cpp
doc/html/boost_asio/example/cpp03/http/server/reply.cpp
doc/html/boost_asio/example/cpp03/http/server/connection.hpp
doc/html/boost_asio/example/cpp03/http/server/connection.cpp
doc/html/boost_asio/example/cpp03/http/server/reply.hpp
doc/html/boost_asio/example/cpp03/http/server/server.hpp
doc/html/boost_asio/example/cpp03/http/server/server.cpp
doc/html/boost_asio/example/cpp03/http/client/sync_client.cpp
doc/html/boost_asio/example/cpp03/http/client/async_client.cpp
doc/html/boost_asio/example/cpp03/http/server4/reply.cpp
doc/html/boost_asio/example/cpp03/http/server4/reply.hpp
doc/html/boost_asio/example/cpp03/http/server4/server.hpp
doc/html/boost_asio/example/cpp03/http/server4/request_parser.hpp
doc/html/boost_asio/example/cpp03/http/server4/main.cpp
doc/html/boost_asio/example/cpp03/http/server4/server.cpp
doc/html/boost_asio/example/cpp03/http/server2/reply.cpp
doc/html/boost_asio/example/cpp03/http/server2/connection.hpp
doc/html/boost_asio/example/cpp03/http/server2/connection.cpp
doc/html/boost_asio/example/cpp03/http/server2/io_context_pool.hpp
doc/html/boost_asio/example/cpp03/http/server2/reply.hpp
doc/html/boost_asio/example/cpp03/http/server2/server.hpp
doc/html/boost_asio/example/cpp03/http/server2/io_context_pool.cpp
doc/html/boost_asio/example/cpp03/http/server2/server.cpp
doc/html/boost_asio/example/cpp03/http/server3/reply.cpp
doc/html/boost_asio/example/cpp03/http/server3/connection.hpp
doc/html/boost_asio/example/cpp03/http/server3/connection.cpp
doc/html/boost_asio/example/cpp03/http/server3/reply.hpp
doc/html/boost_asio/example/cpp03/http/server3/server.hpp
doc/html/boost_asio/example/cpp03/http/server3/server.cpp
doc/html/boost_asio/example/cpp03/windows/transmit_file.cpp
doc/html/boost_asio/example/cpp03/iostreams/daytime_client.cpp
doc/html/boost_asio/example/cpp03/iostreams/http_client.cpp
doc/html/boost_asio/example/cpp03/iostreams/daytime_server.cpp
doc/html/boost_asio/example/cpp03/local/stream_client.cpp
doc/html/boost_asio/example/cpp03/local/iostream_client.cpp
doc/html/boost_asio/example/cpp03/local/stream_server.cpp
doc/html/boost_asio/example/cpp03/local/connect_pair.cpp
doc/html/boost_asio/example/cpp03/serialization/connection.hpp
doc/html/boost_asio/example/cpp03/serialization/client.cpp
doc/html/boost_asio/example/cpp03/serialization/server.cpp
doc/html/boost_asio/example/cpp03/invocation/prioritised_handlers.cpp
doc/html/boost_asio/example/cpp03/porthopper/client.cpp
doc/html/boost_asio/example/cpp03/porthopper/protocol.hpp
doc/html/boost_asio/example/cpp03/porthopper/server.cpp
doc/html/boost_asio/example/cpp11/timers/time_t_timer.cpp
doc/html/boost_asio/example/cpp11/handler_tracking/custom_tracking.hpp
doc/html/boost_asio/example/cpp11/handler_tracking/async_tcp_echo_server.cpp
doc/html/boost_asio/example/cpp11/spawn/parallel_grep.cpp
doc/html/boost_asio/example/cpp11/spawn/echo_server.cpp
doc/html/boost_asio/example/cpp11/chat/chat_server.cpp
doc/html/boost_asio/example/cpp11/chat/chat_client.cpp
doc/html/boost_asio/example/cpp11/ssl/client.cpp
doc/html/boost_asio/example/cpp11/ssl/server.cpp
doc/html/boost_asio/example/cpp11/buffers/reference_counted.cpp
doc/html/boost_asio/example/cpp11/multicast/sender.cpp
doc/html/boost_asio/example/cpp11/multicast/receiver.cpp
doc/html/boost_asio/example/cpp11/timeouts/blocking_tcp_client.cpp
doc/html/boost_asio/example/cpp11/timeouts/blocking_token_tcp_client.cpp
doc/html/boost_asio/example/cpp11/timeouts/async_tcp_client.cpp
doc/html/boost_asio/example/cpp11/timeouts/server.cpp
doc/html/boost_asio/example/cpp11/timeouts/blocking_udp_client.cpp
doc/html/boost_asio/example/cpp11/socks4/socks4.hpp
doc/html/boost_asio/example/cpp11/socks4/sync_client.cpp
doc/html/boost_asio/example/cpp11/executors/actor.cpp
doc/html/boost_asio/example/cpp11/executors/priority_scheduler.cpp
doc/html/boost_asio/example/cpp11/executors/bank_account_2.cpp
doc/html/boost_asio/example/cpp11/executors/bank_account_1.cpp
doc/html/boost_asio/example/cpp11/executors/fork_join.cpp
doc/html/boost_asio/example/cpp11/executors/pipeline.cpp
doc/html/boost_asio/example/cpp11/operations/composed_4.cpp
doc/html/boost_asio/example/cpp11/operations/composed_5.cpp
doc/html/boost_asio/example/cpp11/operations/composed_1.cpp
doc/html/boost_asio/example/cpp11/operations/composed_2.cpp
doc/html/boost_asio/example/cpp11/operations/composed_3.cpp
doc/html/boost_asio/example/cpp11/echo/blocking_tcp_echo_server.cpp
doc/html/boost_asio/example/cpp11/echo/blocking_tcp_echo_client.cpp
doc/html/boost_asio/example/cpp11/echo/blocking_udp_echo_server.cpp
doc/html/boost_asio/example/cpp11/echo/blocking_udp_echo_client.cpp
doc/html/boost_asio/example/cpp11/echo/async_tcp_echo_server.cpp
doc/html/boost_asio/example/cpp11/echo/async_udp_echo_server.cpp
doc/html/boost_asio/example/cpp11/allocation/server.cpp
doc/html/boost_asio/example/cpp11/fork/daemon.cpp
doc/html/boost_asio/example/cpp11/fork/process_per_connection.cpp
doc/html/boost_asio/example/cpp11/http/server/reply.cpp
doc/html/boost_asio/example/cpp11/http/server/connection.hpp
doc/html/boost_asio/example/cpp11/http/server/connection.cpp
doc/html/boost_asio/example/cpp11/http/server/reply.hpp
doc/html/boost_asio/example/cpp11/http/server/server.hpp
doc/html/boost_asio/example/cpp11/http/server/server.cpp
doc/html/boost_asio/example/cpp11/futures/daytime_client.cpp
doc/html/boost_asio/example/cpp11/local/stream_client.cpp
doc/html/boost_asio/example/cpp11/local/iostream_client.cpp
doc/html/boost_asio/example/cpp11/local/stream_server.cpp
doc/html/boost_asio/example/cpp11/local/connect_pair.cpp
doc/html/boost_asio/example/cpp11/invocation/prioritised_handlers.cpp
doc/html/boost_asio/overview/signals.html
doc/html/boost_asio/overview/core/line_based.html
doc/html/boost_asio/overview/core/coroutine.html
doc/html/boost_asio/overview/core/strands.html
doc/html/boost_asio/overview/core/allocation.html
doc/html/boost_asio/overview/core/coroutines_ts.html
doc/html/boost_asio/overview/core/spawn.html
doc/html/boost_asio/overview/cpp2011/move_handlers.html
doc/html/boost_asio/overview/cpp2011/futures.html
doc/html/boost_asio/overview/networking/other_protocols.html
doc/html/boost_asio/overview/networking/protocols.html
doc/html/boost_asio/overview/posix/fork.html
doc/html/boost_asio/overview/posix/stream_descriptor.html
doc/html/boost_asio/overview/ssl.html
doc/html/boost_asio/index.html
doc/html/boost_asio/reference/io_context__service/get_io_service.html
doc/html/boost_asio/reference/io_context__service/get_io_context.html
doc/html/boost_asio/reference/io_context__service/service.html
doc/html/boost_asio/reference/ip__multicast__outbound_interface.html
doc/html/boost_asio/reference/transfer_all.html
doc/html/boost_asio/reference/is_error_code_enum_lt__boost__asio__ssl__error__stream_errors__gt_.html
doc/html/boost_asio/reference/AcceptHandler.html
doc/html/boost_asio/reference/io_context.html
doc/html/boost_asio/reference/io_service.html
doc/html/boost_asio/reference/RangeConnectHandler.html
doc/html/boost_asio/reference/io_context__strand/get_io_service.html
doc/html/boost_asio/reference/io_context__strand/strand.html
doc/html/boost_asio/reference/io_context__strand/get_io_context.html
doc/html/boost_asio/reference/io_context__strand/context.html
doc/html/boost_asio/reference/is_error_code_enum_lt__netdb_errors__gt_/value.html
doc/html/boost_asio/reference/spawn/overload6.html
doc/html/boost_asio/reference/windows__overlapped_ptr/reset.html
doc/html/boost_asio/reference/windows__overlapped_ptr/overlapped_ptr.html
doc/html/boost_asio/reference/windows__overlapped_ptr/overlapped_ptr/overload2.html
doc/html/boost_asio/reference/windows__overlapped_ptr/reset/overload2.html
doc/html/boost_asio/reference/signal_set.html
doc/html/boost_asio/reference/ResolveHandler.html
doc/html/boost_asio/reference/ReadHandler.html
doc/html/boost_asio/reference/basic_socket_iostream/expires_after.html
doc/html/boost_asio/reference/basic_socket_iostream/expires_from_now/overload2.html
doc/html/boost_asio/reference/basic_socket_iostream/expires_at/overload2.html
doc/html/boost_asio/reference/ConstBufferSequence.html
doc/html/boost_asio/reference/mutable_buffers_1/value_type.html
doc/html/boost_asio/reference/is_error_code_enum_lt__basic_errors__gt_/value.html
doc/html/boost_asio/reference/const_buffer.html
doc/html/boost_asio/reference/is_error_code_enum_lt__addrinfo_errors__gt_/value.html
doc/html/boost_asio/reference/is_error_code_enum_lt__boost__asio__ssl__error__stream_errors__gt_/value.html
doc/html/boost_asio/reference/null_buffers/value_type.html
doc/html/boost_asio/reference/ip__basic_endpoint/basic_endpoint.html
doc/html/boost_asio/reference/ip__basic_endpoint/address.html
doc/html/boost_asio/reference/ip__basic_endpoint/address/overload2.html
doc/html/boost_asio/reference/ip__basic_endpoint/address/overload1.html
doc/html/boost_asio/reference/ip__basic_endpoint/basic_endpoint/overload2.html
doc/html/boost_asio/reference/ip__basic_endpoint/basic_endpoint/overload3.html
doc/html/boost_asio/reference/async_read_until.html
doc/html/boost_asio/reference/buffer_sequence_end.html
doc/html/boost_asio/reference/posix__descriptor_base/bytes_readable.html
doc/html/boost_asio/reference/placeholders__signal_number.html
doc/html/boost_asio/reference/ip__v6_only.html
doc/html/boost_asio/reference/high_resolution_timer.html
doc/html/boost_asio/reference/thread_pool/make_service.html
doc/html/boost_asio/reference/thread_pool/add_service.html
doc/html/boost_asio/reference/system_timer.html
doc/html/boost_asio/reference/buffer_size.html
doc/html/boost_asio/reference/const_buffers_1/value_type.html
doc/html/boost_asio/reference/mutable_buffer.html
doc/html/boost_asio/reference/MutableBufferSequence.html
doc/html/boost_asio/reference/basic_streambuf.html
doc/html/boost_asio/reference/execution_context/make_service.html
doc/html/boost_asio/reference/execution_context/add_service.html
doc/html/boost_asio/reference/io_context__strand.html
doc/html/boost_asio/reference/buffer_sequence_begin.html
doc/html/boost_asio/reference/async_read_at/overload2.html
doc/html/boost_asio/reference/async_read_at/overload4.html
doc/html/boost_asio/reference/async_read_at/overload1.html
doc/html/boost_asio/reference/async_read_at/overload3.html
doc/html/boost_asio/reference/error__netdb_category.html
doc/html/boost_asio/reference/transfer_exactly.html
doc/html/boost_asio/reference/error__ssl_category.html
doc/html/boost_asio/reference/async_read_until/overload2.html
doc/html/boost_asio/reference/async_read_until/overload5.html
doc/html/boost_asio/reference/async_read_until/overload7.html
doc/html/boost_asio/reference/async_read_until/overload8.html
doc/html/boost_asio/reference/async_read_until/overload4.html
doc/html/boost_asio/reference/async_read_until/overload6.html
doc/html/boost_asio/reference/async_read_until/overload1.html
doc/html/boost_asio/reference/async_read_until/overload3.html
doc/html/boost_asio/reference/async_connect/overload2.html
doc/html/boost_asio/reference/async_connect/overload5.html
doc/html/boost_asio/reference/async_connect/overload4.html
doc/html/boost_asio/reference/async_connect/overload6.html
doc/html/boost_asio/reference/async_connect/overload1.html
doc/html/boost_asio/reference/async_connect/overload3.html
doc/html/boost_asio/reference/error__system_category.html
doc/html/boost_asio/reference/ConnectHandler.html
doc/html/boost_asio/reference/is_error_code_enum_lt__netdb_errors__gt_.html
doc/html/boost_asio/reference/is_error_code_enum_lt__ssl_errors__gt_/value.html
doc/html/boost_asio/reference/buffer_cast.html
doc/html/boost_asio/reference/is_error_code_enum_lt__ssl_errors__gt_.html
doc/html/boost_asio/reference/basic_seq_packet_socket/get_io_service.html
doc/html/boost_asio/reference/basic_seq_packet_socket/receive_buffer_size.html
doc/html/boost_asio/reference/basic_seq_packet_socket/wait/overload2.html
doc/html/boost_asio/reference/basic_seq_packet_socket/wait/overload1.html
doc/html/boost_asio/reference/basic_seq_packet_socket/keep_alive.html
doc/html/boost_asio/reference/basic_seq_packet_socket/close/overload2.html
doc/html/boost_asio/reference/basic_seq_packet_socket/close/overload1.html
doc/html/boost_asio/reference/basic_seq_packet_socket/local_endpoint/overload2.html
doc/html/boost_asio/reference/basic_seq_packet_socket/local_endpoint/overload1.html
doc/html/boost_asio/reference/basic_seq_packet_socket/send_buffer_size.html
doc/html/boost_asio/reference/basic_seq_packet_socket/reuse_address.html
doc/html/boost_asio/reference/basic_seq_packet_socket/shutdown/overload2.html
doc/html/boost_asio/reference/basic_seq_packet_socket/shutdown/overload1.html
doc/html/boost_asio/reference/basic_seq_packet_socket/async_wait.html
doc/html/boost_asio/reference/basic_seq_packet_socket/cancel/overload2.html
doc/html/boost_asio/reference/basic_seq_packet_socket/cancel/overload1.html
doc/html/boost_asio/reference/basic_seq_packet_socket/debug.html
doc/html/boost_asio/reference/basic_seq_packet_socket/async_connect.html
doc/html/boost_asio/reference/basic_seq_packet_socket/remote_endpoint/overload2.html
doc/html/boost_asio/reference/basic_seq_packet_socket/remote_endpoint/overload1.html
doc/html/boost_asio/reference/basic_seq_packet_socket/io_control/overload2.html
doc/html/boost_asio/reference/basic_seq_packet_socket/io_control/overload1.html
doc/html/boost_asio/reference/basic_seq_packet_socket/linger.html
doc/html/boost_asio/reference/basic_seq_packet_socket/broadcast.html
doc/html/boost_asio/reference/basic_seq_packet_socket/basic_seq_packet_socket/overload2.html
doc/html/boost_asio/reference/basic_seq_packet_socket/basic_seq_packet_socket/overload4.html
doc/html/boost_asio/reference/basic_seq_packet_socket/basic_seq_packet_socket/overload1.html
doc/html/boost_asio/reference/basic_seq_packet_socket/basic_seq_packet_socket/overload3.html
doc/html/boost_asio/reference/basic_seq_packet_socket/enable_connection_aborted.html
doc/html/boost_asio/reference/basic_seq_packet_socket/get_io_context.html
doc/html/boost_asio/reference/basic_seq_packet_socket/set_option/overload2.html
doc/html/boost_asio/reference/basic_seq_packet_socket/set_option/overload1.html
doc/html/boost_asio/reference/basic_seq_packet_socket/connect/overload2.html
doc/html/boost_asio/reference/basic_seq_packet_socket/connect/overload1.html
doc/html/boost_asio/reference/basic_seq_packet_socket/native_non_blocking/overload2.html
doc/html/boost_asio/reference/basic_seq_packet_socket/native_non_blocking/overload1.html
doc/html/boost_asio/reference/basic_seq_packet_socket/native_non_blocking/overload3.html
doc/html/boost_asio/reference/basic_seq_packet_socket/release/overload2.html
doc/html/boost_asio/reference/basic_seq_packet_socket/release/overload1.html
doc/html/boost_asio/reference/basic_seq_packet_socket/open/overload2.html
doc/html/boost_asio/reference/basic_seq_packet_socket/open/overload1.html
doc/html/boost_asio/reference/basic_seq_packet_socket/receive_low_watermark.html
doc/html/boost_asio/reference/basic_seq_packet_socket/bind/overload2.html
doc/html/boost_asio/reference/basic_seq_packet_socket/bind/overload1.html
doc/html/boost_asio/reference/basic_seq_packet_socket/send_low_watermark.html
doc/html/boost_asio/reference/basic_seq_packet_socket/non_blocking/overload2.html
doc/html/boost_asio/reference/basic_seq_packet_socket/non_blocking/overload1.html
doc/html/boost_asio/reference/basic_seq_packet_socket/non_blocking/overload3.html
doc/html/boost_asio/reference/basic_seq_packet_socket/receive/overload2.html
doc/html/boost_asio/reference/basic_seq_packet_socket/receive/overload1.html
doc/html/boost_asio/reference/basic_seq_packet_socket/get_option/overload2.html
doc/html/boost_asio/reference/basic_seq_packet_socket/get_option/overload1.html
doc/html/boost_asio/reference/basic_seq_packet_socket/do_not_route.html
doc/html/boost_asio/reference/basic_seq_packet_socket/async_receive/overload2.html
doc/html/boost_asio/reference/basic_seq_packet_socket/async_receive/overload1.html
doc/html/boost_asio/reference/basic_seq_packet_socket/send/overload1.html
doc/html/boost_asio/reference/basic_seq_packet_socket/out_of_band_inline.html
doc/html/boost_asio/reference/basic_seq_packet_socket/async_send.html
doc/html/boost_asio/reference/basic_seq_packet_socket/bytes_readable.html
doc/html/boost_asio/reference/basic_seq_packet_socket/basic_seq_packet_socket.html
doc/html/boost_asio/reference/ip__multicast__leave_group.html
doc/html/boost_asio/reference/placeholders__results.html
doc/html/boost_asio/reference/ip__tcp/no_delay.html
doc/html/boost_asio/reference/ip__tcp/acceptor.html
doc/html/boost_asio/reference/windows__overlapped_handle/get_io_service.html
doc/html/boost_asio/reference/windows__overlapped_handle/close/overload2.html
doc/html/boost_asio/reference/windows__overlapped_handle/close/overload1.html
doc/html/boost_asio/reference/windows__overlapped_handle/cancel/overload2.html
doc/html/boost_asio/reference/windows__overlapped_handle/cancel/overload1.html
doc/html/boost_asio/reference/windows__overlapped_handle/overlapped_handle/overload2.html
doc/html/boost_asio/reference/windows__overlapped_handle/overlapped_handle/overload1.html
doc/html/boost_asio/reference/windows__overlapped_handle/get_io_context.html
doc/html/boost_asio/reference/windows__overlapped_handle/overlapped_handle.html
doc/html/boost_asio/reference/read_at/overload2.html
doc/html/boost_asio/reference/read_at/overload5.html
doc/html/boost_asio/reference/read_at/overload6.html
doc/html/boost_asio/reference/read_at/overload1.html
doc/html/boost_asio/reference/read_at/overload3.html
doc/html/boost_asio/reference/basic_streambuf_ref/const_buffers_type.html
doc/html/boost_asio/reference/basic_streambuf_ref/mutable_buffers_type.html
doc/html/boost_asio/reference/read_until/overload5.html
doc/html/boost_asio/reference/read_until/overload9.html
doc/html/boost_asio/reference/read_until/overload7.html
doc/html/boost_asio/reference/read_until/overload11.html
doc/html/boost_asio/reference/read_until/overload15.html
doc/html/boost_asio/reference/read_until/overload10.html
doc/html/boost_asio/reference/read_until/overload14.html
doc/html/boost_asio/reference/read_until/overload16.html
doc/html/boost_asio/reference/read_until/overload13.html
doc/html/boost_asio/reference/read_until/overload12.html
doc/html/boost_asio/reference/read_until/overload1.html
doc/html/boost_asio/reference/read_until/overload3.html
doc/html/boost_asio/reference/basic_waitable_timer/get_io_service.html
doc/html/boost_asio/reference/basic_waitable_timer/cancel_one/overload2.html
doc/html/boost_asio/reference/basic_waitable_timer/cancel_one/overload1.html
doc/html/boost_asio/reference/basic_waitable_timer/async_wait.html
doc/html/boost_asio/reference/basic_waitable_timer/cancel/overload2.html
doc/html/boost_asio/reference/basic_waitable_timer/cancel/overload1.html
doc/html/boost_asio/reference/basic_waitable_timer/basic_waitable_timer/overload2.html
doc/html/boost_asio/reference/basic_waitable_timer/basic_waitable_timer/overload1.html
doc/html/boost_asio/reference/basic_waitable_timer/basic_waitable_timer/overload3.html
doc/html/boost_asio/reference/basic_waitable_timer/get_io_context.html
doc/html/boost_asio/reference/basic_waitable_timer/expires_after.html
doc/html/boost_asio/reference/basic_waitable_timer/expires_from_now/overload2.html
doc/html/boost_asio/reference/basic_waitable_timer/expires_from_now/overload3.html
doc/html/boost_asio/reference/basic_waitable_timer/basic_waitable_timer.html
doc/html/boost_asio/reference/basic_waitable_timer/expires_at/overload2.html
doc/html/boost_asio/reference/basic_waitable_timer/expires_at/overload3.html
doc/html/boost_asio/reference/basic_socket_acceptor.html
doc/html/boost_asio/reference/generic__stream_protocol.html
doc/html/boost_asio/reference/is_error_code_enum_lt__misc_errors__gt_.html
doc/html/boost_asio/reference/basic_stream_socket/get_io_service.html
doc/html/boost_asio/reference/basic_stream_socket/receive_buffer_size.html
doc/html/boost_asio/reference/basic_stream_socket/wait/overload2.html
doc/html/boost_asio/reference/basic_stream_socket/wait/overload1.html
doc/html/boost_asio/reference/basic_stream_socket/keep_alive.html
doc/html/boost_asio/reference/basic_stream_socket/close/overload2.html
doc/html/boost_asio/reference/basic_stream_socket/close/overload1.html
doc/html/boost_asio/reference/basic_stream_socket/local_endpoint/overload2.html
doc/html/boost_asio/reference/basic_stream_socket/local_endpoint/overload1.html
doc/html/boost_asio/reference/basic_stream_socket/send_buffer_size.html
doc/html/boost_asio/reference/basic_stream_socket/reuse_address.html
doc/html/boost_asio/reference/basic_stream_socket/shutdown/overload2.html
doc/html/boost_asio/reference/basic_stream_socket/shutdown/overload1.html
doc/html/boost_asio/reference/basic_stream_socket/async_wait.html
doc/html/boost_asio/reference/basic_stream_socket/cancel/overload2.html
doc/html/boost_asio/reference/basic_stream_socket/cancel/overload1.html
doc/html/boost_asio/reference/basic_stream_socket/debug.html
doc/html/boost_asio/reference/basic_stream_socket/async_connect.html
doc/html/boost_asio/reference/basic_stream_socket/async_read_some.html
doc/html/boost_asio/reference/basic_stream_socket/remote_endpoint/overload2.html
doc/html/boost_asio/reference/basic_stream_socket/remote_endpoint/overload1.html
doc/html/boost_asio/reference/basic_stream_socket/io_control/overload2.html
doc/html/boost_asio/reference/basic_stream_socket/io_control/overload1.html
doc/html/boost_asio/reference/basic_stream_socket/linger.html
doc/html/boost_asio/reference/basic_stream_socket/broadcast.html
doc/html/boost_asio/reference/basic_stream_socket/basic_stream_socket.html
doc/html/boost_asio/reference/basic_stream_socket/enable_connection_aborted.html
doc/html/boost_asio/reference/basic_stream_socket/get_io_context.html
doc/html/boost_asio/reference/basic_stream_socket/set_option/overload2.html
doc/html/boost_asio/reference/basic_stream_socket/set_option/overload1.html
doc/html/boost_asio/reference/basic_stream_socket/basic_stream_socket/overload2.html
doc/html/boost_asio/reference/basic_stream_socket/basic_stream_socket/overload4.html
doc/html/boost_asio/reference/basic_stream_socket/basic_stream_socket/overload1.html
doc/html/boost_asio/reference/basic_stream_socket/basic_stream_socket/overload3.html
doc/html/boost_asio/reference/basic_stream_socket/connect/overload2.html
doc/html/boost_asio/reference/basic_stream_socket/connect/overload1.html
doc/html/boost_asio/reference/basic_stream_socket/native_non_blocking/overload2.html
doc/html/boost_asio/reference/basic_stream_socket/native_non_blocking/overload1.html
doc/html/boost_asio/reference/basic_stream_socket/native_non_blocking/overload3.html
doc/html/boost_asio/reference/basic_stream_socket/release/overload2.html
doc/html/boost_asio/reference/basic_stream_socket/release/overload1.html
doc/html/boost_asio/reference/basic_stream_socket/open/overload2.html
doc/html/boost_asio/reference/basic_stream_socket/open/overload1.html
doc/html/boost_asio/reference/basic_stream_socket/write_some/overload1.html
doc/html/boost_asio/reference/basic_stream_socket/receive_low_watermark.html
doc/html/boost_asio/reference/basic_stream_socket/bind/overload2.html
doc/html/boost_asio/reference/basic_stream_socket/bind/overload1.html
doc/html/boost_asio/reference/basic_stream_socket/send_low_watermark.html
doc/html/boost_asio/reference/basic_stream_socket/async_write_some.html
doc/html/boost_asio/reference/basic_stream_socket/non_blocking/overload2.html
doc/html/boost_asio/reference/basic_stream_socket/non_blocking/overload1.html
doc/html/boost_asio/reference/basic_stream_socket/non_blocking/overload3.html
doc/html/boost_asio/reference/basic_stream_socket/receive/overload2.html
doc/html/boost_asio/reference/basic_stream_socket/receive/overload1.html
doc/html/boost_asio/reference/basic_stream_socket/get_option/overload2.html
doc/html/boost_asio/reference/basic_stream_socket/get_option/overload1.html
doc/html/boost_asio/reference/basic_stream_socket/do_not_route.html
doc/html/boost_asio/reference/basic_stream_socket/async_receive/overload2.html
doc/html/boost_asio/reference/basic_stream_socket/async_receive/overload1.html
doc/html/boost_asio/reference/basic_stream_socket/send/overload2.html
doc/html/boost_asio/reference/basic_stream_socket/send/overload1.html
doc/html/boost_asio/reference/basic_stream_socket/read_some/overload1.html
doc/html/boost_asio/reference/basic_stream_socket/out_of_band_inline.html
doc/html/boost_asio/reference/basic_stream_socket/async_send/overload2.html
doc/html/boost_asio/reference/basic_stream_socket/async_send/overload1.html
doc/html/boost_asio/reference/basic_stream_socket/bytes_readable.html
doc/html/boost_asio/reference/IteratorConnectHandler.html
doc/html/boost_asio/reference/is_error_code_enum_lt__misc_errors__gt_/value.html
doc/html/boost_asio/reference/buffered_read_stream/get_io_service.html
doc/html/boost_asio/reference/buffered_read_stream/get_io_context.html
doc/html/boost_asio/reference/io_context__work/get_io_service.html
doc/html/boost_asio/reference/io_context__work/work.html
doc/html/boost_asio/reference/io_context__work/get_io_context.html
doc/html/boost_asio/reference/io_context__work/work/overload1.html
doc/html/boost_asio/reference/connect/overload2.html
doc/html/boost_asio/reference/connect/overload5.html
doc/html/boost_asio/reference/connect/overload9.html
doc/html/boost_asio/reference/connect/overload7.html
doc/html/boost_asio/reference/connect/overload11.html
doc/html/boost_asio/reference/connect/overload8.html
doc/html/boost_asio/reference/connect/overload4.html
doc/html/boost_asio/reference/connect/overload10.html
doc/html/boost_asio/reference/connect/overload6.html
doc/html/boost_asio/reference/connect/overload12.html
doc/html/boost_asio/reference/connect/overload1.html
doc/html/boost_asio/reference/connect/overload3.html
doc/html/boost_asio/reference/windows__object_handle/get_io_service.html
doc/html/boost_asio/reference/windows__object_handle/close/overload2.html
doc/html/boost_asio/reference/windows__object_handle/close/overload1.html
doc/html/boost_asio/reference/windows__object_handle/object_handle/overload2.html
doc/html/boost_asio/reference/windows__object_handle/object_handle/overload1.html
doc/html/boost_asio/reference/windows__object_handle/async_wait.html
doc/html/boost_asio/reference/windows__object_handle/cancel/overload2.html
doc/html/boost_asio/reference/windows__object_handle/cancel/overload1.html
doc/html/boost_asio/reference/windows__object_handle/get_io_context.html
doc/html/boost_asio/reference/windows__object_handle/object_handle.html
doc/html/boost_asio/reference/thread_pool.html
doc/html/boost_asio/reference/error__addrinfo_category.html
doc/html/boost_asio/reference/serial_port/get_io_service.html
doc/html/boost_asio/reference/serial_port/close/overload2.html
doc/html/boost_asio/reference/serial_port/close/overload1.html
doc/html/boost_asio/reference/serial_port/cancel/overload2.html
doc/html/boost_asio/reference/serial_port/cancel/overload1.html
doc/html/boost_asio/reference/serial_port/async_read_some.html
doc/html/boost_asio/reference/serial_port/serial_port.html
doc/html/boost_asio/reference/serial_port/get_io_context.html
doc/html/boost_asio/reference/serial_port/serial_port/overload2.html
doc/html/boost_asio/reference/serial_port/serial_port/overload4.html
doc/html/boost_asio/reference/serial_port/serial_port/overload1.html
doc/html/boost_asio/reference/serial_port/serial_port/overload3.html
doc/html/boost_asio/reference/serial_port/write_some/overload1.html
doc/html/boost_asio/reference/serial_port/async_write_some.html
doc/html/boost_asio/reference/serial_port/read_some/overload1.html
doc/html/boost_asio/reference/buffered_write_stream/get_io_service.html
doc/html/boost_asio/reference/buffered_write_stream/get_io_context.html
doc/html/boost_asio/reference/HandshakeHandler.html
doc/html/boost_asio/reference/WriteHandler.html
doc/html/boost_asio/reference/async_write/overload2.html
doc/html/boost_asio/reference/async_write/overload5.html
doc/html/boost_asio/reference/async_write/overload4.html
doc/html/boost_asio/reference/async_write/overload6.html
doc/html/boost_asio/reference/async_write/overload1.html
doc/html/boost_asio/reference/async_write/overload3.html
doc/html/boost_asio/reference/basic_socket_acceptor/get_io_service.html
doc/html/boost_asio/reference/basic_socket_acceptor/receive_buffer_size.html
doc/html/boost_asio/reference/basic_socket_acceptor/wait/overload2.html
doc/html/boost_asio/reference/basic_socket_acceptor/wait/overload1.html
doc/html/boost_asio/reference/basic_socket_acceptor/async_accept.html
doc/html/boost_asio/reference/basic_socket_acceptor/keep_alive.html
doc/html/boost_asio/reference/basic_socket_acceptor/close/overload2.html
doc/html/boost_asio/reference/basic_socket_acceptor/local_endpoint/overload2.html
doc/html/boost_asio/reference/basic_socket_acceptor/local_endpoint/overload1.html
doc/html/boost_asio/reference/basic_socket_acceptor/send_buffer_size.html
doc/html/boost_asio/reference/basic_socket_acceptor/reuse_address.html
doc/html/boost_asio/reference/basic_socket_acceptor/async_wait.html
doc/html/boost_asio/reference/basic_socket_acceptor/cancel/overload2.html
doc/html/boost_asio/reference/basic_socket_acceptor/cancel/overload1.html
doc/html/boost_asio/reference/basic_socket_acceptor/listen/overload2.html
doc/html/boost_asio/reference/basic_socket_acceptor/debug.html
doc/html/boost_asio/reference/basic_socket_acceptor/io_control/overload2.html
doc/html/boost_asio/reference/basic_socket_acceptor/io_control/overload1.html
doc/html/boost_asio/reference/basic_socket_acceptor/linger.html
doc/html/boost_asio/reference/basic_socket_acceptor/broadcast.html
doc/html/boost_asio/reference/basic_socket_acceptor/enable_connection_aborted.html
doc/html/boost_asio/reference/basic_socket_acceptor/accept/overload2.html
doc/html/boost_asio/reference/basic_socket_acceptor/accept/overload5.html
doc/html/boost_asio/reference/basic_socket_acceptor/accept/overload9.html
doc/html/boost_asio/reference/basic_socket_acceptor/accept/overload7.html
doc/html/boost_asio/reference/basic_socket_acceptor/accept/overload11.html
doc/html/boost_asio/reference/basic_socket_acceptor/accept/overload8.html
doc/html/boost_asio/reference/basic_socket_acceptor/accept/overload4.html
doc/html/boost_asio/reference/basic_socket_acceptor/accept/overload10.html
doc/html/boost_asio/reference/basic_socket_acceptor/accept/overload6.html
doc/html/boost_asio/reference/basic_socket_acceptor/accept/overload12.html
doc/html/boost_asio/reference/basic_socket_acceptor/accept/overload1.html
doc/html/boost_asio/reference/basic_socket_acceptor/accept/overload3.html
doc/html/boost_asio/reference/basic_socket_acceptor/get_io_context.html
doc/html/boost_asio/reference/basic_socket_acceptor/basic_socket_acceptor.html
doc/html/boost_asio/reference/basic_socket_acceptor/set_option/overload2.html
doc/html/boost_asio/reference/basic_socket_acceptor/set_option/overload1.html
doc/html/boost_asio/reference/basic_socket_acceptor/native_non_blocking/overload2.html
doc/html/boost_asio/reference/basic_socket_acceptor/native_non_blocking/overload1.html
doc/html/boost_asio/reference/basic_socket_acceptor/native_non_blocking/overload3.html
doc/html/boost_asio/reference/basic_socket_acceptor/release/overload2.html
doc/html/boost_asio/reference/basic_socket_acceptor/release/overload1.html
doc/html/boost_asio/reference/basic_socket_acceptor/open/overload2.html
doc/html/boost_asio/reference/basic_socket_acceptor/open/overload1.html
doc/html/boost_asio/reference/basic_socket_acceptor/basic_socket_acceptor/overload2.html
doc/html/boost_asio/reference/basic_socket_acceptor/basic_socket_acceptor/overload4.html
doc/html/boost_asio/reference/basic_socket_acceptor/basic_socket_acceptor/overload1.html
doc/html/boost_asio/reference/basic_socket_acceptor/basic_socket_acceptor/overload3.html
doc/html/boost_asio/reference/basic_socket_acceptor/receive_low_watermark.html
doc/html/boost_asio/reference/basic_socket_acceptor/bind/overload2.html
doc/html/boost_asio/reference/basic_socket_acceptor/bind/overload1.html
doc/html/boost_asio/reference/basic_socket_acceptor/send_low_watermark.html
doc/html/boost_asio/reference/basic_socket_acceptor/non_blocking/overload2.html
doc/html/boost_asio/reference/basic_socket_acceptor/non_blocking/overload1.html
doc/html/boost_asio/reference/basic_socket_acceptor/non_blocking/overload3.html
doc/html/boost_asio/reference/basic_socket_acceptor/get_option/overload2.html
doc/html/boost_asio/reference/basic_socket_acceptor/get_option/overload1.html
doc/html/boost_asio/reference/basic_socket_acceptor/do_not_route.html
doc/html/boost_asio/reference/basic_socket_acceptor/async_accept/overload2.html
doc/html/boost_asio/reference/basic_socket_acceptor/async_accept/overload5.html
doc/html/boost_asio/reference/basic_socket_acceptor/async_accept/overload4.html
doc/html/boost_asio/reference/basic_socket_acceptor/async_accept/overload6.html
doc/html/boost_asio/reference/basic_socket_acceptor/async_accept/overload1.html
doc/html/boost_asio/reference/basic_socket_acceptor/async_accept/overload3.html
doc/html/boost_asio/reference/basic_socket_acceptor/out_of_band_inline.html
doc/html/boost_asio/reference/basic_socket_acceptor/bytes_readable.html
doc/html/boost_asio/reference/basic_socket_acceptor/accept.html
doc/html/boost_asio/reference/dynamic_string_buffer/const_buffers_type.html
doc/html/boost_asio/reference/dynamic_string_buffer/mutable_buffers_type.html
doc/html/boost_asio/reference/generic__datagram_protocol.html
doc/html/boost_asio/reference/placeholders__iterator.html
doc/html/boost_asio/reference/ip__basic_resolver/get_io_service.html
doc/html/boost_asio/reference/ip__basic_resolver/basic_resolver/overload1.html
doc/html/boost_asio/reference/ip__basic_resolver/async_resolve/overload2.html
doc/html/boost_asio/reference/ip__basic_resolver/async_resolve/overload5.html
doc/html/boost_asio/reference/ip__basic_resolver/async_resolve/overload4.html
doc/html/boost_asio/reference/ip__basic_resolver/async_resolve/overload6.html
doc/html/boost_asio/reference/ip__basic_resolver/async_resolve/overload1.html
doc/html/boost_asio/reference/ip__basic_resolver/async_resolve/overload3.html
doc/html/boost_asio/reference/ip__basic_resolver/cancel.html
doc/html/boost_asio/reference/ip__basic_resolver/get_io_context.html
doc/html/boost_asio/reference/ip__basic_resolver/basic_resolver.html
doc/html/boost_asio/reference/ip__address/to_v4.html
doc/html/boost_asio/reference/ip__address/operator_eq_.html
doc/html/boost_asio/reference/ip__address/operator_eq_/overload2.html
doc/html/boost_asio/reference/ip__address/operator_eq_/overload3.html
doc/html/boost_asio/reference/ip__address/to_v6.html
doc/html/boost_asio/reference/ip__address/address.html
doc/html/boost_asio/reference/ip__address/address/overload2.html
doc/html/boost_asio/reference/ip__address/address/overload3.html
doc/html/boost_asio/reference/buffer_copy.html
doc/html/boost_asio/reference/signal_set/get_io_service.html
doc/html/boost_asio/reference/signal_set/signal_set.html
doc/html/boost_asio/reference/signal_set/async_wait.html
doc/html/boost_asio/reference/signal_set/cancel/overload2.html
doc/html/boost_asio/reference/signal_set/cancel/overload1.html
doc/html/boost_asio/reference/signal_set/get_io_context.html
doc/html/boost_asio/reference/signal_set/signal_set/overload2.html
doc/html/boost_asio/reference/signal_set/signal_set/overload4.html
doc/html/boost_asio/reference/signal_set/signal_set/overload1.html
doc/html/boost_asio/reference/signal_set/signal_set/overload3.html
doc/html/boost_asio/reference/windows__stream_handle/stream_handle.html
doc/html/boost_asio/reference/windows__stream_handle/get_io_service.html
doc/html/boost_asio/reference/windows__stream_handle/close/overload2.html
doc/html/boost_asio/reference/windows__stream_handle/close/overload1.html
doc/html/boost_asio/reference/windows__stream_handle/cancel/overload2.html
doc/html/boost_asio/reference/windows__stream_handle/cancel/overload1.html
doc/html/boost_asio/reference/windows__stream_handle/async_read_some.html
doc/html/boost_asio/reference/windows__stream_handle/stream_handle/overload2.html
doc/html/boost_asio/reference/windows__stream_handle/stream_handle/overload1.html
doc/html/boost_asio/reference/windows__stream_handle/get_io_context.html
doc/html/boost_asio/reference/windows__stream_handle/write_some/overload1.html
doc/html/boost_asio/reference/windows__stream_handle/async_write_some.html
doc/html/boost_asio/reference/windows__stream_handle/read_some/overload1.html
doc/html/boost_asio/reference/steady_timer.html
doc/html/boost_asio/reference/basic_socket/get_io_service.html
doc/html/boost_asio/reference/basic_socket/receive_buffer_size.html
doc/html/boost_asio/reference/basic_socket/wait/overload2.html
doc/html/boost_asio/reference/basic_socket/wait/overload1.html
doc/html/boost_asio/reference/basic_socket/keep_alive.html
doc/html/boost_asio/reference/basic_socket/close/overload2.html
doc/html/boost_asio/reference/basic_socket/close/overload1.html
doc/html/boost_asio/reference/basic_socket/local_endpoint/overload2.html
doc/html/boost_asio/reference/basic_socket/local_endpoint/overload1.html
doc/html/boost_asio/reference/basic_socket/send_buffer_size.html
doc/html/boost_asio/reference/basic_socket/reuse_address.html
doc/html/boost_asio/reference/basic_socket/shutdown/overload2.html
doc/html/boost_asio/reference/basic_socket/shutdown/overload1.html
doc/html/boost_asio/reference/basic_socket/async_wait.html
doc/html/boost_asio/reference/basic_socket/cancel/overload2.html
doc/html/boost_asio/reference/basic_socket/cancel/overload1.html
doc/html/boost_asio/reference/basic_socket/debug.html
doc/html/boost_asio/reference/basic_socket/async_connect.html
doc/html/boost_asio/reference/basic_socket/remote_endpoint/overload2.html
doc/html/boost_asio/reference/basic_socket/remote_endpoint/overload1.html
doc/html/boost_asio/reference/basic_socket/io_control/overload2.html
doc/html/boost_asio/reference/basic_socket/io_control/overload1.html
doc/html/boost_asio/reference/basic_socket/linger.html
doc/html/boost_asio/reference/basic_socket/broadcast.html
doc/html/boost_asio/reference/basic_socket/enable_connection_aborted.html
doc/html/boost_asio/reference/basic_socket/get_io_context.html
doc/html/boost_asio/reference/basic_socket/set_option/overload2.html
doc/html/boost_asio/reference/basic_socket/set_option/overload1.html
doc/html/boost_asio/reference/basic_socket/connect/overload2.html
doc/html/boost_asio/reference/basic_socket/connect/overload1.html
doc/html/boost_asio/reference/basic_socket/native_non_blocking/overload2.html
doc/html/boost_asio/reference/basic_socket/native_non_blocking/overload1.html
doc/html/boost_asio/reference/basic_socket/native_non_blocking/overload3.html
doc/html/boost_asio/reference/basic_socket/release/overload2.html
doc/html/boost_asio/reference/basic_socket/release/overload1.html
doc/html/boost_asio/reference/basic_socket/open/overload2.html
doc/html/boost_asio/reference/basic_socket/open/overload1.html
doc/html/boost_asio/reference/basic_socket/basic_socket.html
doc/html/boost_asio/reference/basic_socket/receive_low_watermark.html
doc/html/boost_asio/reference/basic_socket/bind/overload2.html
doc/html/boost_asio/reference/basic_socket/bind/overload1.html
doc/html/boost_asio/reference/basic_socket/basic_socket/overload2.html
doc/html/boost_asio/reference/basic_socket/basic_socket/overload4.html
doc/html/boost_asio/reference/basic_socket/basic_socket/overload1.html
doc/html/boost_asio/reference/basic_socket/basic_socket/overload3.html
doc/html/boost_asio/reference/basic_socket/send_low_watermark.html
doc/html/boost_asio/reference/basic_socket/non_blocking/overload2.html
doc/html/boost_asio/reference/basic_socket/non_blocking/overload1.html
doc/html/boost_asio/reference/basic_socket/non_blocking/overload3.html
doc/html/boost_asio/reference/basic_socket/get_option/overload2.html
doc/html/boost_asio/reference/basic_socket/get_option/overload1.html
doc/html/boost_asio/reference/basic_socket/do_not_route.html
doc/html/boost_asio/reference/basic_socket/out_of_band_inline.html
doc/html/boost_asio/reference/basic_socket/bytes_readable.html
doc/html/boost_asio/reference/read/overload2.html
doc/html/boost_asio/reference/read/overload5.html
doc/html/boost_asio/reference/read/overload9.html
doc/html/boost_asio/reference/read/overload10.html
doc/html/boost_asio/reference/read/overload6.html
doc/html/boost_asio/reference/read/overload1.html
doc/html/boost_asio/reference/read/overload3.html
doc/html/boost_asio/reference/posix__stream_descriptor/get_io_service.html
doc/html/boost_asio/reference/posix__stream_descriptor/wait/overload2.html
doc/html/boost_asio/reference/posix__stream_descriptor/wait/overload1.html
doc/html/boost_asio/reference/posix__stream_descriptor/close/overload2.html
doc/html/boost_asio/reference/posix__stream_descriptor/close/overload1.html
doc/html/boost_asio/reference/posix__stream_descriptor/async_wait.html
doc/html/boost_asio/reference/posix__stream_descriptor/cancel/overload2.html
doc/html/boost_asio/reference/posix__stream_descriptor/cancel/overload1.html
doc/html/boost_asio/reference/posix__stream_descriptor/async_read_some.html
doc/html/boost_asio/reference/posix__stream_descriptor/release.html
doc/html/boost_asio/reference/posix__stream_descriptor/io_control/overload2.html
doc/html/boost_asio/reference/posix__stream_descriptor/io_control/overload1.html
doc/html/boost_asio/reference/posix__stream_descriptor/get_io_context.html
doc/html/boost_asio/reference/posix__stream_descriptor/native_non_blocking/overload2.html
doc/html/boost_asio/reference/posix__stream_descriptor/native_non_blocking/overload1.html
doc/html/boost_asio/reference/posix__stream_descriptor/native_non_blocking/overload3.html
doc/html/boost_asio/reference/posix__stream_descriptor/stream_descriptor/overload2.html
doc/html/boost_asio/reference/posix__stream_descriptor/stream_descriptor/overload1.html
doc/html/boost_asio/reference/posix__stream_descriptor/stream_descriptor.html
doc/html/boost_asio/reference/posix__stream_descriptor/write_some/overload1.html
doc/html/boost_asio/reference/posix__stream_descriptor/async_write_some.html
doc/html/boost_asio/reference/posix__stream_descriptor/non_blocking/overload2.html
doc/html/boost_asio/reference/posix__stream_descriptor/non_blocking/overload1.html
doc/html/boost_asio/reference/posix__stream_descriptor/non_blocking/overload3.html
doc/html/boost_asio/reference/posix__stream_descriptor/read_some/overload1.html
doc/html/boost_asio/reference/posix__stream_descriptor/bytes_readable.html
doc/html/boost_asio/reference/streambuf.html
doc/html/boost_asio/reference/basic_deadline_timer.html
doc/html/boost_asio/reference/async_write_at/overload2.html
doc/html/boost_asio/reference/async_write_at/overload4.html
doc/html/boost_asio/reference/async_write_at/overload1.html
doc/html/boost_asio/reference/async_write_at/overload3.html
doc/html/boost_asio/reference/Handler.html
doc/html/boost_asio/reference/dynamic_buffer.html
doc/html/boost_asio/reference/ip__multicast__join_group.html
doc/html/boost_asio/reference/ip__multicast__hops.html
doc/html/boost_asio/reference/error__misc_category.html
doc/html/boost_asio/reference/yield_context.html
doc/html/boost_asio/reference/use_future_t.html
doc/html/boost_asio/reference/is_error_code_enum_lt__basic_errors__gt_.html
doc/html/boost_asio/reference/MoveAcceptHandler.html
doc/html/boost_asio/reference/posix__descriptor/get_io_service.html
doc/html/boost_asio/reference/posix__descriptor/wait/overload2.html
doc/html/boost_asio/reference/posix__descriptor/wait/overload1.html
doc/html/boost_asio/reference/posix__descriptor/descriptor.html
doc/html/boost_asio/reference/posix__descriptor/close/overload2.html
doc/html/boost_asio/reference/posix__descriptor/close/overload1.html
doc/html/boost_asio/reference/posix__descriptor/async_wait.html
doc/html/boost_asio/reference/posix__descriptor/cancel/overload2.html
doc/html/boost_asio/reference/posix__descriptor/cancel/overload1.html
doc/html/boost_asio/reference/posix__descriptor/release.html
doc/html/boost_asio/reference/posix__descriptor/io_control/overload2.html
doc/html/boost_asio/reference/posix__descriptor/io_control/overload1.html
doc/html/boost_asio/reference/posix__descriptor/get_io_context.html
doc/html/boost_asio/reference/posix__descriptor/native_non_blocking/overload2.html
doc/html/boost_asio/reference/posix__descriptor/native_non_blocking/overload1.html
doc/html/boost_asio/reference/posix__descriptor/native_non_blocking/overload3.html
doc/html/boost_asio/reference/posix__descriptor/non_blocking/overload2.html
doc/html/boost_asio/reference/posix__descriptor/non_blocking/overload1.html
doc/html/boost_asio/reference/posix__descriptor/non_blocking/overload3.html
doc/html/boost_asio/reference/posix__descriptor/descriptor/overload2.html
doc/html/boost_asio/reference/posix__descriptor/descriptor/overload1.html
doc/html/boost_asio/reference/posix__descriptor/bytes_readable.html
doc/html/boost_asio/reference/ssl__stream/get_io_service.html
doc/html/boost_asio/reference/ssl__stream/native_handle.html
doc/html/boost_asio/reference/ssl__stream/get_io_context.html
doc/html/boost_asio/reference/SignalHandler.html
doc/html/boost_asio/reference/ip__basic_resolver_query/hints.html
doc/html/boost_asio/reference/ssl__stream.html
doc/html/boost_asio/reference/basic_deadline_timer/get_io_service.html
doc/html/boost_asio/reference/basic_deadline_timer/cancel_one/overload2.html
doc/html/boost_asio/reference/basic_deadline_timer/cancel_one/overload1.html
doc/html/boost_asio/reference/basic_deadline_timer/async_wait.html
doc/html/boost_asio/reference/basic_deadline_timer/cancel/overload2.html
doc/html/boost_asio/reference/basic_deadline_timer/cancel/overload1.html
doc/html/boost_asio/reference/basic_deadline_timer/get_io_context.html
doc/html/boost_asio/reference/basic_deadline_timer/basic_deadline_timer.html
doc/html/boost_asio/reference/basic_deadline_timer/expires_from_now/overload2.html
doc/html/boost_asio/reference/basic_deadline_timer/expires_from_now/overload3.html
doc/html/boost_asio/reference/basic_deadline_timer/basic_deadline_timer/overload2.html
doc/html/boost_asio/reference/basic_deadline_timer/basic_deadline_timer/overload1.html
doc/html/boost_asio/reference/basic_deadline_timer/basic_deadline_timer/overload3.html
doc/html/boost_asio/reference/basic_deadline_timer/expires_at/overload2.html
doc/html/boost_asio/reference/basic_deadline_timer/expires_at/overload3.html
doc/html/boost_asio/reference/placeholders__bytes_transferred.html
doc/html/boost_asio/reference/ssl__error__stream_category.html
doc/html/boost_asio/reference/spawn.html
doc/html/boost_asio/reference/async_completion/completion_handler_type.html
doc/html/boost_asio/reference/ShutdownHandler.html
doc/html/boost_asio/reference/io_context/make_service.html
doc/html/boost_asio/reference/io_context/add_service.html
doc/html/boost_asio/reference/write_at/overload2.html
doc/html/boost_asio/reference/write_at/overload5.html
doc/html/boost_asio/reference/write_at/overload6.html
doc/html/boost_asio/reference/write_at/overload1.html
doc/html/boost_asio/reference/write_at/overload3.html
doc/html/boost_asio/reference/transfer_at_least.html
doc/html/boost_asio/reference/BufferedHandshakeHandler.html
doc/html/boost_asio/reference/placeholders__endpoint.html
doc/html/boost_asio/reference/WaitHandler.html
doc/html/boost_asio/reference/deadline_timer.html
doc/html/boost_asio/reference/async_read/overload2.html
doc/html/boost_asio/reference/async_read/overload5.html
doc/html/boost_asio/reference/async_read/overload4.html
doc/html/boost_asio/reference/async_read/overload6.html
doc/html/boost_asio/reference/async_read/overload1.html
doc/html/boost_asio/reference/async_read/overload3.html
doc/html/boost_asio/reference/local__stream_protocol/acceptor.html
doc/html/boost_asio/reference/basic_io_object/get_io_service.html
doc/html/boost_asio/reference/basic_io_object/executor_type.html
doc/html/boost_asio/reference/basic_io_object/basic_io_object.html
doc/html/boost_asio/reference/basic_io_object/get_io_context.html
doc/html/boost_asio/reference/basic_io_object/basic_io_object/overload1.html
doc/html/boost_asio/reference/basic_socket_streambuf/expires_after.html
doc/html/boost_asio/reference/basic_socket_streambuf/expires_from_now/overload2.html
doc/html/boost_asio/reference/basic_socket_streambuf/expires_at/overload2.html
doc/html/boost_asio/reference/ip__multicast__enable_loopback.html
doc/html/boost_asio/reference/ssl__rfc2818_verification.html
doc/html/boost_asio/reference/basic_waitable_timer.html
doc/html/boost_asio/reference/ip__unicast__hops.html
doc/html/boost_asio/reference/basic_raw_socket/get_io_service.html
doc/html/boost_asio/reference/basic_raw_socket/receive_buffer_size.html
doc/html/boost_asio/reference/basic_raw_socket/wait/overload2.html
doc/html/boost_asio/reference/basic_raw_socket/wait/overload1.html
doc/html/boost_asio/reference/basic_raw_socket/keep_alive.html
doc/html/boost_asio/reference/basic_raw_socket/close/overload2.html
doc/html/boost_asio/reference/basic_raw_socket/close/overload1.html
doc/html/boost_asio/reference/basic_raw_socket/local_endpoint/overload2.html
doc/html/boost_asio/reference/basic_raw_socket/local_endpoint/overload1.html
doc/html/boost_asio/reference/basic_raw_socket/send_buffer_size.html
doc/html/boost_asio/reference/basic_raw_socket/reuse_address.html
doc/html/boost_asio/reference/basic_raw_socket/shutdown/overload2.html
doc/html/boost_asio/reference/basic_raw_socket/shutdown/overload1.html
doc/html/boost_asio/reference/basic_raw_socket/send_to/overload1.html
doc/html/boost_asio/reference/basic_raw_socket/async_wait.html
doc/html/boost_asio/reference/basic_raw_socket/cancel/overload2.html
doc/html/boost_asio/reference/basic_raw_socket/cancel/overload1.html
doc/html/boost_asio/reference/basic_raw_socket/debug.html
doc/html/boost_asio/reference/basic_raw_socket/async_connect.html
doc/html/boost_asio/reference/basic_raw_socket/receive_from/overload1.html
doc/html/boost_asio/reference/basic_raw_socket/remote_endpoint/overload2.html
doc/html/boost_asio/reference/basic_raw_socket/remote_endpoint/overload1.html
doc/html/boost_asio/reference/basic_raw_socket/io_control/overload2.html
doc/html/boost_asio/reference/basic_raw_socket/io_control/overload1.html
doc/html/boost_asio/reference/basic_raw_socket/linger.html
doc/html/boost_asio/reference/basic_raw_socket/broadcast.html
doc/html/boost_asio/reference/basic_raw_socket/enable_connection_aborted.html
doc/html/boost_asio/reference/basic_raw_socket/get_io_context.html
doc/html/boost_asio/reference/basic_raw_socket/set_option/overload2.html
doc/html/boost_asio/reference/basic_raw_socket/set_option/overload1.html
doc/html/boost_asio/reference/basic_raw_socket/connect/overload2.html
doc/html/boost_asio/reference/basic_raw_socket/connect/overload1.html
doc/html/boost_asio/reference/basic_raw_socket/native_non_blocking/overload2.html
doc/html/boost_asio/reference/basic_raw_socket/native_non_blocking/overload1.html
doc/html/boost_asio/reference/basic_raw_socket/native_non_blocking/overload3.html
doc/html/boost_asio/reference/basic_raw_socket/release/overload2.html
doc/html/boost_asio/reference/basic_raw_socket/release/overload1.html
doc/html/boost_asio/reference/basic_raw_socket/open/overload2.html
doc/html/boost_asio/reference/basic_raw_socket/open/overload1.html
doc/html/boost_asio/reference/basic_raw_socket/receive_low_watermark.html
doc/html/boost_asio/reference/basic_raw_socket/bind/overload2.html
doc/html/boost_asio/reference/basic_raw_socket/bind/overload1.html
doc/html/boost_asio/reference/basic_raw_socket/send_low_watermark.html
doc/html/boost_asio/reference/basic_raw_socket/non_blocking/overload2.html
doc/html/boost_asio/reference/basic_raw_socket/non_blocking/overload1.html
doc/html/boost_asio/reference/basic_raw_socket/non_blocking/overload3.html
doc/html/boost_asio/reference/basic_raw_socket/receive/overload1.html
doc/html/boost_asio/reference/basic_raw_socket/get_option/overload2.html
doc/html/boost_asio/reference/basic_raw_socket/get_option/overload1.html
doc/html/boost_asio/reference/basic_raw_socket/async_receive_from/overload2.html
doc/html/boost_asio/reference/basic_raw_socket/async_receive_from/overload1.html
doc/html/boost_asio/reference/basic_raw_socket/do_not_route.html
doc/html/boost_asio/reference/basic_raw_socket/async_receive/overload2.html
doc/html/boost_asio/reference/basic_raw_socket/async_receive/overload1.html
doc/html/boost_asio/reference/basic_raw_socket/send/overload1.html
doc/html/boost_asio/reference/basic_raw_socket/basic_raw_socket.html
doc/html/boost_asio/reference/basic_raw_socket/basic_raw_socket/overload2.html
doc/html/boost_asio/reference/basic_raw_socket/basic_raw_socket/overload4.html
doc/html/boost_asio/reference/basic_raw_socket/basic_raw_socket/overload1.html
doc/html/boost_asio/reference/basic_raw_socket/basic_raw_socket/overload3.html
doc/html/boost_asio/reference/basic_raw_socket/out_of_band_inline.html
doc/html/boost_asio/reference/basic_raw_socket/async_send/overload2.html
doc/html/boost_asio/reference/basic_raw_socket/async_send/overload1.html
doc/html/boost_asio/reference/basic_raw_socket/async_send_to/overload2.html
doc/html/boost_asio/reference/basic_raw_socket/async_send_to/overload1.html
doc/html/boost_asio/reference/basic_raw_socket/bytes_readable.html
doc/html/boost_asio/reference/windows__random_access_handle/get_io_service.html
doc/html/boost_asio/reference/windows__random_access_handle/close/overload2.html
doc/html/boost_asio/reference/windows__random_access_handle/close/overload1.html
doc/html/boost_asio/reference/windows__random_access_handle/cancel/overload2.html
doc/html/boost_asio/reference/windows__random_access_handle/cancel/overload1.html
doc/html/boost_asio/reference/windows__random_access_handle/random_access_handle/overload2.html
doc/html/boost_asio/reference/windows__random_access_handle/random_access_handle/overload1.html
doc/html/boost_asio/reference/windows__random_access_handle/get_io_context.html
doc/html/boost_asio/reference/windows__random_access_handle/random_access_handle.html
doc/html/boost_asio/reference/windows__random_access_handle/write_some_at/overload1.html
doc/html/boost_asio/reference/windows__random_access_handle/read_some_at/overload1.html
doc/html/boost_asio/reference/windows__random_access_handle/async_write_some_at.html
doc/html/boost_asio/reference/windows__random_access_handle/async_read_some_at.html
doc/html/boost_asio/reference/is_error_code_enum_lt__addrinfo_errors__gt_.html
doc/html/boost_asio/reference/buffer.html
doc/html/boost_asio/reference/add_service.html
doc/html/boost_asio/reference/buffered_stream/get_io_service.html
doc/html/boost_asio/reference/buffered_stream/get_io_context.html
doc/html/boost_asio/reference/read_until.html
doc/html/boost_asio/reference/experimental__detached_t.html
doc/html/boost_asio/reference/generic__raw_protocol.html
doc/html/boost_asio/reference/basic_datagram_socket/get_io_service.html
doc/html/boost_asio/reference/basic_datagram_socket/receive_buffer_size.html
doc/html/boost_asio/reference/basic_datagram_socket/wait/overload2.html
doc/html/boost_asio/reference/basic_datagram_socket/wait/overload1.html
doc/html/boost_asio/reference/basic_datagram_socket/keep_alive.html
doc/html/boost_asio/reference/basic_datagram_socket/close/overload2.html
doc/html/boost_asio/reference/basic_datagram_socket/close/overload1.html
doc/html/boost_asio/reference/basic_datagram_socket/local_endpoint/overload2.html
doc/html/boost_asio/reference/basic_datagram_socket/local_endpoint/overload1.html
doc/html/boost_asio/reference/basic_datagram_socket/send_buffer_size.html
doc/html/boost_asio/reference/basic_datagram_socket/reuse_address.html
doc/html/boost_asio/reference/basic_datagram_socket/shutdown/overload2.html
doc/html/boost_asio/reference/basic_datagram_socket/shutdown/overload1.html
doc/html/boost_asio/reference/basic_datagram_socket/send_to/overload1.html
doc/html/boost_asio/reference/basic_datagram_socket/async_wait.html
doc/html/boost_asio/reference/basic_datagram_socket/cancel/overload2.html
doc/html/boost_asio/reference/basic_datagram_socket/cancel/overload1.html
doc/html/boost_asio/reference/basic_datagram_socket/debug.html
doc/html/boost_asio/reference/basic_datagram_socket/async_connect.html
doc/html/boost_asio/reference/basic_datagram_socket/receive_from/overload1.html
doc/html/boost_asio/reference/basic_datagram_socket/remote_endpoint/overload2.html
doc/html/boost_asio/reference/basic_datagram_socket/remote_endpoint/overload1.html
doc/html/boost_asio/reference/basic_datagram_socket/io_control/overload2.html
doc/html/boost_asio/reference/basic_datagram_socket/io_control/overload1.html
doc/html/boost_asio/reference/basic_datagram_socket/linger.html
doc/html/boost_asio/reference/basic_datagram_socket/broadcast.html
doc/html/boost_asio/reference/basic_datagram_socket/enable_connection_aborted.html
doc/html/boost_asio/reference/basic_datagram_socket/get_io_context.html
doc/html/boost_asio/reference/basic_datagram_socket/set_option/overload2.html
doc/html/boost_asio/reference/basic_datagram_socket/set_option/overload1.html
doc/html/boost_asio/reference/basic_datagram_socket/connect/overload2.html
doc/html/boost_asio/reference/basic_datagram_socket/connect/overload1.html
doc/html/boost_asio/reference/basic_datagram_socket/native_non_blocking/overload2.html
doc/html/boost_asio/reference/basic_datagram_socket/native_non_blocking/overload1.html
doc/html/boost_asio/reference/basic_datagram_socket/native_non_blocking/overload3.html
doc/html/boost_asio/reference/basic_datagram_socket/release/overload2.html
doc/html/boost_asio/reference/basic_datagram_socket/release/overload1.html
doc/html/boost_asio/reference/basic_datagram_socket/open/overload2.html
doc/html/boost_asio/reference/basic_datagram_socket/open/overload1.html
doc/html/boost_asio/reference/basic_datagram_socket/receive_low_watermark.html
doc/html/boost_asio/reference/basic_datagram_socket/bind/overload2.html
doc/html/boost_asio/reference/basic_datagram_socket/bind/overload1.html
doc/html/boost_asio/reference/basic_datagram_socket/send_low_watermark.html
doc/html/boost_asio/reference/basic_datagram_socket/non_blocking/overload2.html
doc/html/boost_asio/reference/basic_datagram_socket/non_blocking/overload1.html
doc/html/boost_asio/reference/basic_datagram_socket/non_blocking/overload3.html
doc/html/boost_asio/reference/basic_datagram_socket/receive/overload1.html
doc/html/boost_asio/reference/basic_datagram_socket/get_option/overload2.html
doc/html/boost_asio/reference/basic_datagram_socket/get_option/overload1.html
doc/html/boost_asio/reference/basic_datagram_socket/async_receive_from/overload2.html
doc/html/boost_asio/reference/basic_datagram_socket/async_receive_from/overload1.html
doc/html/boost_asio/reference/basic_datagram_socket/do_not_route.html
doc/html/boost_asio/reference/basic_datagram_socket/async_receive/overload2.html
doc/html/boost_asio/reference/basic_datagram_socket/async_receive/overload1.html
doc/html/boost_asio/reference/basic_datagram_socket/send/overload1.html
doc/html/boost_asio/reference/basic_datagram_socket/basic_datagram_socket.html
doc/html/boost_asio/reference/basic_datagram_socket/out_of_band_inline.html
doc/html/boost_asio/reference/basic_datagram_socket/async_send/overload2.html
doc/html/boost_asio/reference/basic_datagram_socket/async_send/overload1.html
doc/html/boost_asio/reference/basic_datagram_socket/async_send_to/overload2.html
doc/html/boost_asio/reference/basic_datagram_socket/async_send_to/overload1.html
doc/html/boost_asio/reference/basic_datagram_socket/bytes_readable.html
doc/html/boost_asio/reference/basic_datagram_socket/basic_datagram_socket/overload2.html
doc/html/boost_asio/reference/basic_datagram_socket/basic_datagram_socket/overload4.html
doc/html/boost_asio/reference/basic_datagram_socket/basic_datagram_socket/overload1.html
doc/html/boost_asio/reference/basic_datagram_socket/basic_datagram_socket/overload3.html
doc/html/boost_asio/reference/socket_base/receive_buffer_size.html
doc/html/boost_asio/reference/socket_base/keep_alive.html
doc/html/boost_asio/reference/socket_base/send_buffer_size.html
doc/html/boost_asio/reference/socket_base/reuse_address.html
doc/html/boost_asio/reference/socket_base/debug.html
doc/html/boost_asio/reference/socket_base/linger.html
doc/html/boost_asio/reference/socket_base/broadcast.html
doc/html/boost_asio/reference/socket_base/enable_connection_aborted.html
doc/html/boost_asio/reference/socket_base/receive_low_watermark.html
doc/html/boost_asio/reference/socket_base/send_low_watermark.html
doc/html/boost_asio/reference/socket_base/do_not_route.html
doc/html/boost_asio/reference/socket_base/out_of_band_inline.html
doc/html/boost_asio/reference/socket_base/bytes_readable.html
doc/html/boost_asio/reference/dynamic_vector_buffer/const_buffers_type.html
doc/html/boost_asio/reference/dynamic_vector_buffer/mutable_buffers_type.html
doc/html/boost_asio/reference/write/overload2.html
doc/html/boost_asio/reference/write/overload5.html
doc/html/boost_asio/reference/write/overload9.html
doc/html/boost_asio/reference/write/overload10.html
doc/html/boost_asio/reference/write/overload6.html
doc/html/boost_asio/reference/write/overload1.html
doc/html/boost_asio/reference/write/overload3.html
doc/html/boost_asio/reference/system_context/make_service.html
doc/html/boost_asio/reference/system_context/add_service.html
doc/html/boost_asio/net_ts.html
doc/html/boost_asio/tutorial/tutdaytime6.html
doc/html/boost_asio/tutorial/tuttimer2.html
doc/html/boost_asio/tutorial/tuttimer3.html
doc/html/boost_asio/tutorial/tutdaytime4/src.html
doc/html/boost_asio/tutorial/tutdaytime3.html
doc/html/boost_asio/tutorial/tuttimer5/src.html
doc/html/boost_asio/tutorial/tutdaytime7/src.html
doc/html/boost_asio/tutorial/tutdaytime3/src.html
doc/html/boost_asio/tutorial/tutdaytime1.html
doc/html/boost_asio/tutorial/tuttimer2/src.html
doc/html/boost_asio/tutorial/tutdaytime7.html
doc/html/boost_asio/tutorial/tuttimer1/src.html
doc/html/boost_asio/tutorial/tutdaytime4.html
doc/html/boost_asio/tutorial/tutdaytime1/src.html
doc/html/boost_asio/tutorial/tutdaytime5/src.html
doc/html/boost_asio/tutorial/tutdaytime2/src.html
doc/html/boost_asio/tutorial/tuttimer4/src.html
doc/html/boost_asio/tutorial/tutdaytime6/src.html
doc/html/boost_asio/tutorial/tuttimer3/src.html
doc/html/boost_asio/tutorial/tuttimer5.html
doc/html/boost_asio/tutorial/tuttimer1.html
doc/html/boost_asio/tutorial/tutdaytime5.html
doc/html/boost_asio/tutorial/tuttimer4.html
doc/html/boost_asio/tutorial/tutdaytime2.html
doc/html/boost_asio/examples/cpp11_examples.html
doc/html/boost_asio/examples/cpp03_examples.html
doc/html/process/reference.html
doc/html/boost_process/extend.html
doc/html/boost_process/tutorial.html
doc/html/boost/process/on_exit.html
doc/html/boost/process/std_out.html
doc/html/boost/process/std_in.html
doc/html/boost/process/async_pipe.html
doc/html/boost/process/spawn.html
boost/process/detail/async_handler.hpp
boost/process/detail/traits/async.hpp
boost/process/detail/posix/async_out.hpp
boost/process/detail/posix/io_context_ref.hpp
boost/process/detail/posix/async_in.hpp
boost/process/detail/posix/async_pipe.hpp
boost/process/detail/posix/sigchld_service.hpp
boost/process/detail/windows/async_out.hpp
boost/process/detail/windows/io_context_ref.hpp
boost/process/detail/windows/async_in.hpp
boost/process/detail/windows/async_pipe.hpp
boost/process/io.hpp
boost/process/async_system.hpp
boost/process/async.hpp
boost/process/async_pipe.hpp
boost/process/spawn.hpp
boost/process/system.hpp
boost/log/sinks/syslog_backend.hpp
boost/beast/core/detail/bind_handler.hpp
boost/beast/core/detail/buffers_ref.hpp
boost/beast/core/detail/type_traits.hpp
boost/beast/core/flat_buffer.hpp
boost/beast/core/buffers_to_string.hpp
boost/beast/core/buffers_suffix.hpp
boost/beast/core/buffers_cat.hpp
boost/beast/core/impl/flat_buffer.ipp
boost/beast/core/impl/static_buffer.ipp
boost/beast/core/impl/buffers_suffix.ipp
boost/beast/core/impl/read_size.ipp
boost/beast/core/impl/multi_buffer.ipp
boost/beast/core/impl/buffered_read_stream.ipp
boost/beast/core/impl/flat_static_buffer.ipp
boost/beast/core/impl/handler_ptr.ipp
boost/beast/core/impl/buffers_adapter.ipp
boost/beast/core/impl/buffers_prefix.ipp
boost/beast/core/impl/buffers_cat.ipp
boost/beast/core/flat_static_buffer.hpp
boost/beast/core/static_buffer.hpp
boost/beast/core/bind_handler.hpp
boost/beast/core/multi_buffer.hpp
boost/beast/core/ostream.hpp
boost/beast/core/buffers_adapter.hpp
boost/beast/core/buffers_prefix.hpp
boost/beast/core/buffered_read_stream.hpp
boost/beast/core/type_traits.hpp
boost/beast/websocket/stream.hpp
boost/beast/websocket/detail/utf8_checker.hpp
boost/beast/websocket/detail/mask.hpp
boost/beast/websocket/detail/pausation.hpp
boost/beast/websocket/detail/frame.hpp
boost/beast/websocket/detail/stream_base.hpp
boost/beast/websocket/rfc6455.hpp
boost/beast/websocket/teardown.hpp
boost/beast/websocket/ssl.hpp
boost/beast/websocket/impl/close.ipp
boost/beast/websocket/impl/ping.ipp
boost/beast/websocket/impl/ssl.ipp
boost/beast/websocket/impl/teardown.ipp
boost/beast/websocket/impl/stream.ipp
boost/beast/websocket/impl/write.ipp
boost/beast/websocket/impl/accept.ipp
boost/beast/websocket/impl/handshake.ipp
boost/beast/websocket/impl/read.ipp
boost/beast/websocket/role.hpp
boost/beast/experimental/core/timeout_service.hpp
boost/beast/experimental/core/detail/timeout_service.hpp
boost/beast/experimental/core/detail/flat_stream.hpp
boost/beast/experimental/core/detail/service_base.hpp
boost/beast/experimental/core/detail/impl/timeout_service.ipp
boost/beast/experimental/core/flat_stream.hpp
boost/beast/experimental/core/ssl_stream.hpp
boost/beast/experimental/core/impl/flat_stream.ipp
boost/beast/experimental/core/impl/timeout_service.ipp
boost/beast/experimental/core/impl/timeout_socket.hpp
boost/beast/experimental/core/timeout_socket.hpp
boost/beast/experimental/http/impl/icy_stream.ipp
boost/beast/experimental/http/icy_stream.hpp
boost/beast/experimental/test/stream.hpp
boost/beast/experimental/test/impl/stream.ipp
boost/beast/http/string_body.hpp
boost/beast/http/detail/chunk_encode.hpp
boost/beast/http/serializer.hpp
boost/beast/http/basic_file_body.hpp
boost/beast/http/vector_body.hpp
boost/beast/http/parser.hpp
boost/beast/http/impl/basic_parser.ipp
boost/beast/http/impl/file_body_win32.ipp
boost/beast/http/impl/fields.ipp
boost/beast/http/impl/chunk_encode.ipp
boost/beast/http/impl/write.ipp
boost/beast/http/impl/serializer.ipp
boost/beast/http/impl/read.ipp
boost/beast/http/buffer_body.hpp
boost/beast/http/read.hpp
boost/beast/http/basic_dynamic_body.hpp
boost/beast/http/empty_body.hpp
boost/beast/http/error.hpp
boost/beast/http/write.hpp
boost/beast/http/fields.hpp
boost/beast/http/basic_parser.hpp
boost/beast/http/chunk_encode.hpp
boost/beast/http/type_traits.hpp
boost/beast/http/span_body.hpp
boost/asio/io_context.hpp
boost/asio/basic_streambuf.hpp
boost/asio/detail/winapp_thread.hpp
boost/asio/detail/epoll_reactor.hpp
boost/asio/detail/kqueue_reactor.hpp
boost/asio/detail/winrt_ssocket_service_base.hpp
boost/asio/detail/win_iocp_socket_send_op.hpp
boost/asio/detail/resolve_query_op.hpp
boost/asio/detail/winrt_socket_connect_op.hpp
boost/asio/detail/noncopyable.hpp
boost/asio/detail/winrt_socket_recv_op.hpp
boost/asio/detail/win_iocp_socket_accept_op.hpp
boost/asio/detail/dev_poll_reactor.hpp
boost/asio/detail/signal_handler.hpp
boost/asio/detail/buffered_stream_storage.hpp
boost/asio/detail/reactive_socket_service_base.hpp
boost/asio/detail/win_iocp_socket_recv_op.hpp
boost/asio/detail/handler_invoke_helpers.hpp
boost/asio/detail/winsock_init.hpp
boost/asio/detail/reactive_descriptor_service.hpp
boost/asio/detail/descriptor_read_op.hpp
boost/asio/detail/conditionally_enabled_event.hpp
boost/asio/detail/winrt_utils.hpp
boost/asio/detail/winrt_socket_send_op.hpp
boost/asio/detail/deadline_timer_service.hpp
boost/asio/detail/consuming_buffers.hpp
boost/asio/detail/win_iocp_socket_recvfrom_op.hpp
boost/asio/detail/timer_queue.hpp
boost/asio/detail/reactive_serial_port_service.hpp
boost/asio/detail/winrt_resolver_service.hpp
boost/asio/detail/win_iocp_socket_connect_op.hpp
boost/asio/detail/thread_group.hpp
boost/asio/detail/is_buffer_sequence.hpp
boost/asio/detail/reactive_socket_service.hpp
boost/asio/detail/win_static_mutex.hpp
boost/asio/detail/reactive_socket_recvfrom_op.hpp
boost/asio/detail/win_mutex.hpp
boost/asio/detail/winrt_resolve_op.hpp
boost/asio/detail/win_iocp_serial_port_service.hpp
boost/asio/detail/win_iocp_handle_write_op.hpp
boost/asio/detail/std_static_mutex.hpp
boost/asio/detail/resolver_service.hpp
boost/asio/detail/winrt_async_manager.hpp
boost/asio/detail/win_iocp_socket_service_base.hpp
boost/asio/detail/completion_handler.hpp
boost/asio/detail/win_iocp_overlapped_ptr.hpp
boost/asio/detail/impl/socket_ops.ipp
boost/asio/detail/impl/throw_error.ipp
boost/asio/detail/impl/posix_tss_ptr.ipp
boost/asio/detail/impl/dev_poll_reactor.hpp
boost/asio/detail/impl/win_object_handle_service.ipp
boost/asio/detail/impl/posix_event.ipp
boost/asio/detail/impl/win_iocp_socket_service_base.ipp
boost/asio/detail/impl/win_iocp_handle_service.ipp
boost/asio/detail/impl/service_registry.ipp
boost/asio/detail/impl/select_reactor.ipp
boost/asio/detail/impl/reactive_serial_port_service.ipp
boost/asio/detail/impl/handler_tracking.ipp
boost/asio/detail/impl/signal_set_service.ipp
boost/asio/detail/impl/win_thread.ipp
boost/asio/detail/impl/win_mutex.ipp
boost/asio/detail/impl/kqueue_reactor.ipp
boost/asio/detail/impl/scheduler.ipp
boost/asio/detail/impl/strand_service.ipp
boost/asio/detail/impl/posix_thread.ipp
boost/asio/detail/impl/win_iocp_io_context.hpp
boost/asio/detail/impl/socket_select_interrupter.ipp
boost/asio/detail/impl/select_reactor.hpp
boost/asio/detail/impl/win_event.ipp
boost/asio/detail/impl/epoll_reactor.ipp
boost/asio/detail/impl/winrt_timer_scheduler.ipp
boost/asio/detail/impl/strand_executor_service.ipp
boost/asio/detail/impl/dev_poll_reactor.ipp
boost/asio/detail/impl/win_iocp_io_context.ipp
boost/asio/detail/impl/win_static_mutex.ipp
boost/asio/detail/impl/strand_service.hpp
boost/asio/detail/impl/eventfd_select_interrupter.ipp
boost/asio/detail/impl/reactive_descriptor_service.ipp
boost/asio/detail/impl/buffer_sequence_adapter.ipp
boost/asio/detail/impl/resolver_service_base.ipp
boost/asio/detail/impl/win_tss_ptr.ipp
boost/asio/detail/impl/descriptor_ops.ipp
boost/asio/detail/impl/pipe_select_interrupter.ipp
boost/asio/detail/impl/winsock_init.ipp
boost/asio/detail/impl/win_iocp_serial_port_service.ipp
boost/asio/detail/impl/winrt_timer_scheduler.hpp
boost/asio/detail/impl/winrt_ssocket_service_base.ipp
boost/asio/detail/impl/posix_mutex.ipp
boost/asio/detail/impl/reactive_socket_service_base.ipp
boost/asio/detail/socket_option.hpp
boost/asio/detail/null_reactor.hpp
boost/asio/detail/win_iocp_io_context.hpp
boost/asio/detail/reactive_socket_sendto_op.hpp
boost/asio/detail/winrt_ssocket_service.hpp
boost/asio/detail/win_iocp_handle_read_op.hpp
boost/asio/detail/null_thread.hpp
boost/asio/detail/win_object_handle_service.hpp
boost/asio/detail/win_iocp_null_buffers_op.hpp
boost/asio/detail/scheduler.hpp
boost/asio/detail/null_mutex.hpp
boost/asio/detail/handler_cont_helpers.hpp
boost/asio/detail/handler_tracking.hpp
boost/asio/detail/select_reactor.hpp
boost/asio/detail/reactive_socket_connect_op.hpp
boost/asio/detail/posix_mutex.hpp
boost/asio/detail/win_iocp_wait_op.hpp
boost/asio/detail/reactive_socket_recvmsg_op.hpp
boost/asio/detail/resolve_endpoint_op.hpp
boost/asio/detail/reactive_null_buffers_op.hpp
boost/asio/detail/handler_alloc_helpers.hpp
boost/asio/detail/wait_handler.hpp
boost/asio/detail/signal_set_service.hpp
boost/asio/detail/win_iocp_overlapped_op.hpp
boost/asio/detail/buffer_sequence_adapter.hpp
boost/asio/detail/wince_thread.hpp
boost/asio/detail/reactive_socket_recv_op.hpp
boost/asio/detail/descriptor_ops.hpp
boost/asio/detail/strand_service.hpp
boost/asio/detail/descriptor_write_op.hpp
boost/asio/detail/service_registry.hpp
boost/asio/detail/handler_type_requirements.hpp
boost/asio/detail/conditionally_enabled_mutex.hpp
boost/asio/detail/win_iocp_handle_service.hpp
boost/asio/detail/reactive_socket_send_op.hpp
boost/asio/detail/reactive_wait_op.hpp
boost/asio/detail/null_static_mutex.hpp
boost/asio/detail/std_mutex.hpp
boost/asio/detail/win_iocp_socket_recvmsg_op.hpp
boost/asio/detail/null_socket_service.hpp
boost/asio/detail/win_iocp_socket_service.hpp
boost/asio/detail/posix_static_mutex.hpp
boost/asio/detail/resolver_service_base.hpp
boost/asio/detail/reactive_socket_accept_op.hpp
boost/asio/detail/reactor_op_queue.hpp
boost/asio/detail/winrt_timer_scheduler.hpp
boost/asio/detail/string_view.hpp
boost/asio/serial_port_service.hpp
boost/asio/handler_invoke_hook.hpp
boost/asio/basic_serial_port.hpp
boost/asio/basic_deadline_timer.hpp
boost/asio/basic_socket_iostream.hpp
boost/asio/ssl/stream.hpp
boost/asio/ssl/detail/buffered_handshake_op.hpp
boost/asio/ssl/detail/io.hpp
boost/asio/ssl/detail/stream_core.hpp
boost/asio/ssl/detail/openssl_init.hpp
boost/asio/ssl/detail/read_op.hpp
boost/asio/ssl/detail/write_op.hpp
boost/asio/ssl/detail/impl/openssl_init.ipp
boost/asio/ssl/detail/impl/engine.ipp
boost/asio/ssl/detail/engine.hpp
boost/asio/ssl/context.hpp
boost/asio/ssl/impl/context.hpp
boost/asio/ssl/impl/context.ipp
boost/asio/ssl/impl/error.ipp
boost/asio/ssl/context_base.hpp
boost/asio/ssl/rfc2818_verification.hpp
boost/asio/ssl/stream_base.hpp
boost/asio/ssl/error.hpp
boost/asio/completion_condition.hpp
boost/asio/is_executor.hpp
boost/asio/deadline_timer_service.hpp
boost/asio/basic_io_object.hpp
boost/asio/stream_socket_service.hpp
boost/asio/connect.hpp
boost/asio/datagram_socket_service.hpp
boost/asio/placeholders.hpp
boost/asio/socket_base.hpp
boost/asio/basic_stream_socket.hpp
boost/asio/uses_executor.hpp
boost/asio/impl/io_context.hpp
boost/asio/impl/serial_port_base.ipp
boost/asio/impl/connect.hpp
boost/asio/impl/execution_context.ipp
boost/asio/impl/read.hpp
boost/asio/impl/io_context.ipp
boost/asio/impl/read_at.hpp
boost/asio/impl/spawn.hpp
boost/asio/impl/read_until.hpp
boost/asio/impl/write_at.hpp
boost/asio/impl/buffered_write_stream.hpp
boost/asio/impl/write.hpp
boost/asio/impl/buffered_read_stream.hpp
boost/asio/execution_context.hpp
boost/asio/thread_pool.hpp
boost/asio/basic_seq_packet_socket.hpp
boost/asio/socket_acceptor_service.hpp
boost/asio/read.hpp
boost/asio/use_future.hpp
boost/asio/experimental/impl/detached.hpp
boost/asio/experimental/impl/co_spawn.hpp
boost/asio/experimental/detached.hpp
boost/asio/basic_signal_set.hpp
boost/asio/posix/descriptor_base.hpp
boost/asio/posix/basic_descriptor.hpp
boost/asio/posix/stream_descriptor.hpp
boost/asio/posix/descriptor.hpp
boost/asio/posix/stream_descriptor_service.hpp
boost/asio/posix/basic_stream_descriptor.hpp
boost/asio/basic_socket.hpp
boost/asio/executor.hpp
boost/asio/buffered_stream.hpp
boost/asio/signal_set_service.hpp
boost/asio/io_context_strand.hpp
boost/asio/windows/object_handle.hpp
boost/asio/windows/random_access_handle.hpp
boost/asio/windows/basic_random_access_handle.hpp
boost/asio/windows/stream_handle_service.hpp
boost/asio/windows/random_access_handle_service.hpp
boost/asio/windows/basic_handle.hpp
boost/asio/windows/stream_handle.hpp
boost/asio/windows/basic_object_handle.hpp
boost/asio/windows/overlapped_ptr.hpp
boost/asio/windows/object_handle_service.hpp
boost/asio/windows/basic_stream_handle.hpp
boost/asio/windows/overlapped_handle.hpp
boost/asio/basic_socket_acceptor.hpp
boost/asio/local/detail/endpoint.hpp
boost/asio/local/detail/impl/endpoint.ipp
boost/asio/local/basic_endpoint.hpp
boost/asio/local/connect_pair.hpp
boost/asio/local/datagram_protocol.hpp
boost/asio/local/stream_protocol.hpp
boost/asio/coroutine.hpp
boost/asio/basic_waitable_timer.hpp
boost/asio/ip/v6_only.hpp
boost/asio/ip/detail/endpoint.hpp
boost/asio/ip/detail/impl/endpoint.ipp
boost/asio/ip/detail/socket_option.hpp
boost/asio/ip/network_v4.hpp
boost/asio/ip/basic_resolver_iterator.hpp
boost/asio/ip/address_v4.hpp
boost/asio/ip/basic_resolver_results.hpp
boost/asio/ip/basic_endpoint.hpp
boost/asio/ip/basic_resolver.hpp
boost/asio/ip/address_v6.hpp
boost/asio/ip/udp.hpp
boost/asio/ip/basic_resolver_entry.hpp
boost/asio/ip/address.hpp
boost/asio/ip/resolver_service.hpp
boost/asio/ip/basic_resolver_query.hpp
boost/asio/ip/impl/network_v4.hpp
boost/asio/ip/impl/address_v6.ipp
boost/asio/ip/impl/address_v4.hpp
boost/asio/ip/impl/basic_endpoint.hpp
boost/asio/ip/impl/network_v4.ipp
boost/asio/ip/impl/address_v6.hpp
boost/asio/ip/impl/address_v4.ipp
boost/asio/ip/impl/address.hpp
boost/asio/ip/impl/host_name.ipp
boost/asio/ip/impl/network_v6.ipp
boost/asio/ip/impl/address.ipp
boost/asio/ip/impl/network_v6.hpp
boost/asio/ip/icmp.hpp
boost/asio/ip/tcp.hpp
boost/asio/ip/multicast.hpp
boost/asio/ip/network_v6.hpp
boost/asio/ip/unicast.hpp
boost/asio/signal_set.hpp
boost/asio/ts/netfwd.hpp
boost/asio/read_at.hpp
boost/asio/spawn.hpp
boost/asio/async_result.hpp
boost/asio/waitable_timer_service.hpp
boost/asio/basic_socket_streambuf.hpp
boost/asio/serial_port.hpp
boost/asio/read_until.hpp
boost/asio/write_at.hpp
boost/asio/buffered_write_stream.hpp
boost/asio/seq_packet_socket_service.hpp
boost/asio/raw_socket_service.hpp
boost/asio/error.hpp
boost/asio/write.hpp
boost/asio/buffer.hpp
boost/asio/generic/detail/endpoint.hpp
boost/asio/generic/detail/impl/endpoint.ipp
boost/asio/generic/raw_protocol.hpp
boost/asio/generic/basic_endpoint.hpp
boost/asio/generic/datagram_protocol.hpp
boost/asio/generic/stream_protocol.hpp
boost/asio/generic/seq_packet_protocol.hpp
boost/asio/buffers_iterator.hpp
boost/asio/buffered_read_stream.hpp
boost/asio/basic_raw_socket.hpp
boost/asio/basic_datagram_socket.hpp
```
Выведем в консоль все файлы, где упоминается последовательность boost::asio.

```sh
./bootstrap.sh
sudo ./b2 install
```
```
Building Boost.Build engine with toolset gcc... tools/build/src/engine/bin.linuxx86_64/b2
Unicode/ICU support for Boost.Regex?... /usr
Backing up existing Boost.Build configuration in project-config.jam.4
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
     http://www.boost.org/build/doc/html/index.html


```
```
Performing configuration checks

    - default address-model    : 64-bit (cached)
    - default architecture     : x86 (cached)
    - C++11 mutex              : yes (cached)
    - lockfree boost::atomic_flag : yes (cached)
    - Boost.Config Feature Check: cxx11_auto_declarations : yes (cached)
    - Boost.Config Feature Check: cxx11_constexpr : yes (cached)
    - Boost.Config Feature Check: cxx11_defaulted_functions : yes (cached)
    - Boost.Config Feature Check: cxx11_final : yes (cached)
    - Boost.Config Feature Check: cxx11_hdr_mutex : yes (cached)
    - Boost.Config Feature Check: cxx11_hdr_tuple : yes (cached)
    - Boost.Config Feature Check: cxx11_lambdas : yes (cached)
    - Boost.Config Feature Check: cxx11_noexcept : yes (cached)
    - Boost.Config Feature Check: cxx11_nullptr : yes (cached)
    - Boost.Config Feature Check: cxx11_rvalue_references : yes (cached)
    - Boost.Config Feature Check: cxx11_template_aliases : yes (cached)
    - Boost.Config Feature Check: cxx11_thread_local : yes (cached)
    - Boost.Config Feature Check: cxx11_variadic_templates : yes (cached)
    - has_icu builds           : no  (cached)
warning: Graph library does not contain MPI-based parallel components.
note: to enable them, add "using mpi ;" to your user-config.jam
    - zlib                     : no  (cached)
    - bzip2                    : no  (cached)
    - lzma                     : no  (cached)
    - zstd                     : no  (cached)
    - iconv (libc)             : yes (cached)
    - icu                      : no  (cached)
    - icu (lib64)              : no  (cached)
    - native-atomic-int32-supported : yes (cached)
    - native-syslog-supported  : yes (cached)
    - pthread-supports-robust-mutexes : yes (cached)
    - compiler-supports-ssse3  : yes (cached)
    - compiler-supports-avx2   : yes (cached)
    - gcc visibility           : yes (cached)
    - long double support      : yes (cached)
warning: skipping optional Message Passing Interface (MPI) library.
note: to enable MPI support, add "using mpi ;" to user-config.jam.
note: to suppress this message, pass "--without-mpi" to bjam.
note: otherwise, you can safely ignore this message.
warning: No python installation configured and autoconfiguration
note: failed.  See http://www.boost.org/libs/python/doc/building.html
note: for configuration instructions or pass --without-python to
note: suppress this message and silently skip all Boost.Python targets
    - libbacktrace builds      : yes (cached)
    - addr2line builds         : yes (cached)
    - WinDbg builds            : no  (cached)
    - WinDbgCached builds      : no  (cached)
    - BOOST_COMP_GNUC >= 4.3.0 : no  (cached)
    - zlib                     : no  (cached)
    - bzip2                    : no  (cached)
    - lzma                     : no  (cached)
    - zstd                     : no  (cached)

Component configuration:

    - atomic                   : building
    - chrono                   : building
    - container                : building
    - context                  : building
    - contract                 : building
    - coroutine                : building
    - date_time                : building
    - exception                : building
    - fiber                    : building
    - filesystem               : building
    - graph                    : building
    - graph_parallel           : building
    - iostreams                : building
    - locale                   : building
    - log                      : building
    - math                     : building
    - mpi                      : building
    - program_options          : building
    - python                   : building
    - random                   : building
    - regex                    : building
    - serialization            : building
    - stacktrace               : building
    - system                   : building
    - test                     : building
    - thread                   : building
    - timer                    : building
    - type_erasure             : building
    - wave                     : building

...patience...
...patience...
...patience...
...patience...
...patience...
...patience...
...found 40622 targets...
...updating 45 targets...
gcc.compile.c++ bin.v2/libs/thread/build/gcc-13.3.0/release/link-static/threadapi-pthread/threading-multi/visibility-hidden/pthread/thread.o
In file included from /usr/include/pthread.h:33,
                 from /usr/include/x86_64-linux-gnu/c++/13/bits/gthr-default.h:35,
                 from /usr/include/x86_64-linux-gnu/c++/13/bits/gthr.h:148,
                 from /usr/include/c++/13/ext/atomicity.h:35,
                 from /usr/include/c++/13/bits/ios_base.h:39,
                 from /usr/include/c++/13/ios:44,
                 from /usr/include/c++/13/ostream:40,
                 from ./boost/system/error_code.hpp:17,
                 from ./boost/system/system_error.hpp:11,
                 from ./boost/thread/exceptions.hpp:22,
                 from ./boost/thread/pthread/thread_data.hpp:10,
                 from ./boost/thread/thread_only.hpp:17,
                 from libs/thread/src/pthread/thread.cpp:11:
./boost/thread/pthread/thread_data.hpp:60:5: error: missing binary operator before token "("
   60 | #if PTHREAD_STACK_MIN > 0
      |     ^~~~~~~~~~~~~~~~~
In file included from ./boost/functional/hash.hpp:6,
                 from ./boost/thread/detail/thread.hpp:38,
                 from ./boost/thread/thread_only.hpp:22:
./boost/container_hash/hash.hpp:130:33: warning: ‘template<class _Arg, class _Result> struct std::unary_function’ is deprecated [-Wdeprecated-declarations]
  130 |         struct hash_base : std::unary_function<T, std::size_t> {};
      |                                 ^~~~~~~~~~~~~~
In file included from /usr/include/c++/13/string:49,
                 from ./boost/thread/exceptions.hpp:20:
/usr/include/c++/13/bits/stl_function.h:117:12: note: declared here
  117 |     struct unary_function
      |            ^~~~~~~~~~~~~~
In file included from ./boost/concept/assert.hpp:35,
                 from ./boost/concept_check.hpp:20,
                 from ./boost/range/concepts.hpp:19,
                 from ./boost/range/size_type.hpp:20,
                 from ./boost/range/size.hpp:21,
                 from ./boost/range/functions.hpp:20,
                 from ./boost/range/iterator_range_core.hpp:38,
                 from ./boost/algorithm/string/iter_find.hpp:19,
                 from ./boost/algorithm/string/split.hpp:16,
                 from libs/thread/src/pthread/thread.cpp:34:
./boost/concept/detail/general.hpp: In instantiation of ‘static void boost::concepts::constraint<Model>::failed() [with Model = boost::algorithm::FinderConcept<boost::algorithm::detail::token_finderF<boost::algorithm::detail::is_any_ofF<char> >, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >]’:
./boost/algorithm/string/iter_find.hpp:77:13:   required from ‘SequenceSequenceT& boost::algorithm::iter_split(SequenceSequenceT&, RangeT&, FinderT) [with SequenceSequenceT = std::vector<std::__cxx11::basic_string<char> >; RangeT = std::__cxx11::basic_string<char>; FinderT = detail::token_finderF<detail::is_any_ofF<char> >]’
./boost/algorithm/string/split.hpp:146:50:   required from ‘SequenceSequenceT& boost::algorithm::split(SequenceSequenceT&, RangeT&, PredicateT, token_compress_mode_type) [with SequenceSequenceT = std::vector<std::__cxx11::basic_string<char> >; RangeT = std::__cxx11::basic_string<char>; PredicateT = detail::is_any_ofF<char>]’
libs/thread/src/pthread/thread.cpp:537:29:   required from here
./boost/concept/detail/general.hpp:47:52: warning: ‘this’ pointer is null [-Wnonnull]
   47 |     static void failed() { ((Model*)0)->constraints(); }
      |                            ~~~~~~~~~~~~~~~~~~~~~~~~^~
In file included from ./boost/algorithm/string/iter_find.hpp:26:
./boost/algorithm/string/concept.hpp:40:18: note: in a call to non-static member function ‘void boost::algorithm::FinderConcept<FinderT, IteratorT>::constraints() [with FinderT = boost::algorithm::detail::token_finderF<boost::algorithm::detail::is_any_ofF<char> >; IteratorT = __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> >]’
   40 |             void constraints()
      |                  ^~~~~~~~~~~
./boost/concept/detail/general.hpp: In instantiation of ‘static void boost::concepts::requirement<boost::concepts::failed************ Model::************>::failed() [with Model = boost::concepts::usage_requirements<boost::CopyConstructible<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > > >]’:
./boost/concept_check.hpp:167:5:   required from ‘struct boost::CopyConstructible<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >’
./boost/range/concepts.hpp:125:16:   required from ‘struct boost::range_detail::IncrementableIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >’
./boost/range/concepts.hpp:147:16:   required from ‘struct boost::range_detail::SinglePassIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >’
./boost/concept/detail/has_constraints.hpp:32:62:   required by substitution of ‘template<class Model> boost::concepts::detail::yes boost::concepts::detail::has_constraints_(Model*, wrap_constraints<Model, (& Model::constraints)>*) [with Model = boost::range_detail::SinglePassIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >]’
./boost/concept/detail/has_constraints.hpp:42:5:   required from ‘const bool boost::concepts::not_satisfied<boost::range_detail::SinglePassIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > > >::value’
./boost/concept/detail/has_constraints.hpp:45:51:   [ skipping 14 instantiation contexts, use -ftemplate-backtrace-limit=0 to disable ]
./boost/iterator/iterator_facade.hpp:901:3:   required from ‘typename boost::iterators::detail::enable_if_interoperable<Derived1, Derived2, typename boost::mpl::apply2<boost::iterators::detail::always_bool2, Derived1, Derived2>::type>::type boost::iterators::operator!=(const iterator_facade<Derived1, V1, TC1, Reference1, Difference1>&, const iterator_facade<Derived2, V2, TC2, Reference2, Difference2>&) [with Derived1 = transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, use_default, use_default>; V1 = std::__cxx11::basic_string<char>; TC1 = forward_traversal_tag; Reference1 = std::__cxx11::basic_string<char>; Difference1 = long int; Derived2 = transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, use_default, use_default>; V2 = std::__cxx11::basic_string<char>; TC2 = forward_traversal_tag; Reference2 = std::__cxx11::basic_string<char>; Difference2 = long int; typename detail::enable_if_interoperable<Derived1, Derived2, typename boost::mpl::apply2<detail::always_bool2, Derived1, Derived2>::type>::type = bool; typename boost::mpl::apply2<detail::always_bool2, Derived1, Derived2>::type = bool]’
/usr/include/c++/13/bits/stl_vector.h:1671:21:   required from ‘void std::vector<_Tp, _Alloc>::_M_range_initialize(_InputIterator, _InputIterator, std::input_iterator_tag) [with _InputIterator = boost::iterators::transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::iterators::use_default, boost::iterators::use_default>; _Tp = std::__cxx11::basic_string<char>; _Alloc = std::allocator<std::__cxx11::basic_string<char> >]’
/usr/include/c++/13/bits/stl_vector.h:711:23:   required from ‘std::vector<_Tp, _Alloc>::vector(_InputIterator, _InputIterator, const allocator_type&) [with _InputIterator = boost::iterators::transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::iterators::use_default, boost::iterators::use_default>; <template-parameter-2-2> = void; _Tp = std::__cxx11::basic_string<char>; _Alloc = std::allocator<std::__cxx11::basic_string<char> >; allocator_type = std::allocator<std::__cxx11::basic_string<char> >]’
./boost/algorithm/string/iter_find.hpp:178:31:   required from ‘SequenceSequenceT& boost::algorithm::iter_split(SequenceSequenceT&, RangeT&, FinderT) [with SequenceSequenceT = std::vector<std::__cxx11::basic_string<char> >; RangeT = std::__cxx11::basic_string<char>; FinderT = detail::token_finderF<detail::is_any_ofF<char> >]’
./boost/algorithm/string/split.hpp:146:50:   required from ‘SequenceSequenceT& boost::algorithm::split(SequenceSequenceT&, RangeT&, PredicateT, token_compress_mode_type) [with SequenceSequenceT = std::vector<std::__cxx11::basic_string<char> >; RangeT = std::__cxx11::basic_string<char>; PredicateT = detail::is_any_ofF<char>]’
libs/thread/src/pthread/thread.cpp:537:29:   required from here
./boost/concept/detail/general.hpp:39:47: warning: ‘this’ pointer is null [-Wnonnull]
   39 |     static void failed() { ((Model*)0)->~Model(); }
      |                            ~~~~~~~~~~~~~~~~~~~^~
In file included from ./boost/concept_check.hpp:31:
./boost/concept/usage.hpp:16:5: note: in a call to non-static member function ‘boost::concepts::usage_requirements<Model>::~usage_requirements() [with Model = boost::CopyConstructible<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >]’
   16 |     ~usage_requirements() { ((Model*)0)->~Model(); }
      |     ^
./boost/concept/detail/general.hpp: In instantiation of ‘static void boost::concepts::requirement<boost::concepts::failed************ Model::************>::failed() [with Model = boost::concepts::usage_requirements<boost::Convertible<boost::iterators::random_access_traversal_tag, boost::iterators::incrementable_traversal_tag> >]’:
./boost/concept_check.hpp:208:5:   required from ‘struct boost::Convertible<boost::iterators::random_access_traversal_tag, boost::iterators::incrementable_traversal_tag>’
./boost/concept/detail/has_constraints.hpp:32:62:   required by substitution of ‘template<class Model> boost::concepts::detail::yes boost::concepts::detail::has_constraints_(Model*, wrap_constraints<Model, (& Model::constraints)>*) [with Model = boost::Convertible<boost::iterators::random_access_traversal_tag, boost::iterators::incrementable_traversal_tag>]’
./boost/concept/detail/has_constraints.hpp:42:5:   required from ‘const bool boost::concepts::not_satisfied<boost::Convertible<boost::iterators::random_access_traversal_tag, boost::iterators::incrementable_traversal_tag> >::value’
./boost/concept/detail/has_constraints.hpp:45:51:   required from ‘struct boost::concepts::not_satisfied<boost::Convertible<boost::iterators::random_access_traversal_tag, boost::iterators::incrementable_traversal_tag> >’
./boost/concept/detail/general.hpp:51:8:   required from ‘struct boost::concepts::requirement_<void (*)(boost::Convertible<boost::iterators::random_access_traversal_tag, boost::iterators::incrementable_traversal_tag>)>’
./boost/iterator/iterator_concepts.hpp:114:7:   [ skipping 18 instantiation contexts, use -ftemplate-backtrace-limit=0 to disable ]
./boost/iterator/iterator_facade.hpp:901:3:   required from ‘typename boost::iterators::detail::enable_if_interoperable<Derived1, Derived2, typename boost::mpl::apply2<boost::iterators::detail::always_bool2, Derived1, Derived2>::type>::type boost::iterators::operator!=(const iterator_facade<Derived1, V1, TC1, Reference1, Difference1>&, const iterator_facade<Derived2, V2, TC2, Reference2, Difference2>&) [with Derived1 = transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, use_default, use_default>; V1 = std::__cxx11::basic_string<char>; TC1 = forward_traversal_tag; Reference1 = std::__cxx11::basic_string<char>; Difference1 = long int; Derived2 = transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, use_default, use_default>; V2 = std::__cxx11::basic_string<char>; TC2 = forward_traversal_tag; Reference2 = std::__cxx11::basic_string<char>; Difference2 = long int; typename detail::enable_if_interoperable<Derived1, Derived2, typename boost::mpl::apply2<detail::always_bool2, Derived1, Derived2>::type>::type = bool; typename boost::mpl::apply2<detail::always_bool2, Derived1, Derived2>::type = bool]’
/usr/include/c++/13/bits/stl_vector.h:1671:21:   required from ‘void std::vector<_Tp, _Alloc>::_M_range_initialize(_InputIterator, _InputIterator, std::input_iterator_tag) [with _InputIterator = boost::iterators::transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::iterators::use_default, boost::iterators::use_default>; _Tp = std::__cxx11::basic_string<char>; _Alloc = std::allocator<std::__cxx11::basic_string<char> >]’
/usr/include/c++/13/bits/stl_vector.h:711:23:   required from ‘std::vector<_Tp, _Alloc>::vector(_InputIterator, _InputIterator, const allocator_type&) [with _InputIterator = boost::iterators::transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::iterators::use_default, boost::iterators::use_default>; <template-parameter-2-2> = void; _Tp = std::__cxx11::basic_string<char>; _Alloc = std::allocator<std::__cxx11::basic_string<char> >; allocator_type = std::allocator<std::__cxx11::basic_string<char> >]’
./boost/algorithm/string/iter_find.hpp:178:31:   required from ‘SequenceSequenceT& boost::algorithm::iter_split(SequenceSequenceT&, RangeT&, FinderT) [with SequenceSequenceT = std::vector<std::__cxx11::basic_string<char> >; RangeT = std::__cxx11::basic_string<char>; FinderT = detail::token_finderF<detail::is_any_ofF<char> >]’
./boost/algorithm/string/split.hpp:146:50:   required from ‘SequenceSequenceT& boost::algorithm::split(SequenceSequenceT&, RangeT&, PredicateT, token_compress_mode_type) [with SequenceSequenceT = std::vector<std::__cxx11::basic_string<char> >; RangeT = std::__cxx11::basic_string<char>; PredicateT = detail::is_any_ofF<char>]’
libs/thread/src/pthread/thread.cpp:537:29:   required from here
./boost/concept/detail/general.hpp:39:47: warning: ‘this’ pointer is null [-Wnonnull]
   39 |     static void failed() { ((Model*)0)->~Model(); }
      |                            ~~~~~~~~~~~~~~~~~~~^~
./boost/concept/usage.hpp:16:5: note: in a call to non-static member function ‘boost::concepts::usage_requirements<Model>::~usage_requirements() [with Model = boost::Convertible<boost::iterators::random_access_traversal_tag, boost::iterators::incrementable_traversal_tag>]’
   16 |     ~usage_requirements() { ((Model*)0)->~Model(); }
      |     ^
./boost/concept/detail/general.hpp: In instantiation of ‘static void boost::concepts::requirement<boost::concepts::failed************ Model::************>::failed() [with Model = boost::Convertible<boost::iterators::random_access_traversal_tag, boost::iterators::incrementable_traversal_tag>]’:
./boost/iterator/iterator_concepts.hpp:114:7:   required from ‘struct boost::range_detail::IncrementableIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >’
./boost/range/concepts.hpp:147:16:   required from ‘struct boost::range_detail::SinglePassIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >’
./boost/concept/detail/has_constraints.hpp:32:62:   required by substitution of ‘template<class Model> boost::concepts::detail::yes boost::concepts::detail::has_constraints_(Model*, wrap_constraints<Model, (& Model::constraints)>*) [with Model = boost::range_detail::SinglePassIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >]’
./boost/concept/detail/has_constraints.hpp:42:5:   required from ‘const bool boost::concepts::not_satisfied<boost::range_detail::SinglePassIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > > >::value’
./boost/concept/detail/has_constraints.hpp:45:51:   required from ‘struct boost::concepts::not_satisfied<boost::range_detail::SinglePassIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > > >’
./boost/concept/detail/general.hpp:51:8:   [ skipping 13 instantiation contexts, use -ftemplate-backtrace-limit=0 to disable ]
./boost/iterator/iterator_facade.hpp:901:3:   required from ‘typename boost::iterators::detail::enable_if_interoperable<Derived1, Derived2, typename boost::mpl::apply2<boost::iterators::detail::always_bool2, Derived1, Derived2>::type>::type boost::iterators::operator!=(const iterator_facade<Derived1, V1, TC1, Reference1, Difference1>&, const iterator_facade<Derived2, V2, TC2, Reference2, Difference2>&) [with Derived1 = transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, use_default, use_default>; V1 = std::__cxx11::basic_string<char>; TC1 = forward_traversal_tag; Reference1 = std::__cxx11::basic_string<char>; Difference1 = long int; Derived2 = transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, use_default, use_default>; V2 = std::__cxx11::basic_string<char>; TC2 = forward_traversal_tag; Reference2 = std::__cxx11::basic_string<char>; Difference2 = long int; typename detail::enable_if_interoperable<Derived1, Derived2, typename boost::mpl::apply2<detail::always_bool2, Derived1, Derived2>::type>::type = bool; typename boost::mpl::apply2<detail::always_bool2, Derived1, Derived2>::type = bool]’
/usr/include/c++/13/bits/stl_vector.h:1671:21:   required from ‘void std::vector<_Tp, _Alloc>::_M_range_initialize(_InputIterator, _InputIterator, std::input_iterator_tag) [with _InputIterator = boost::iterators::transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::iterators::use_default, boost::iterators::use_default>; _Tp = std::__cxx11::basic_string<char>; _Alloc = std::allocator<std::__cxx11::basic_string<char> >]’
/usr/include/c++/13/bits/stl_vector.h:711:23:   required from ‘std::vector<_Tp, _Alloc>::vector(_InputIterator, _InputIterator, const allocator_type&) [with _InputIterator = boost::iterators::transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::iterators::use_default, boost::iterators::use_default>; <template-parameter-2-2> = void; _Tp = std::__cxx11::basic_string<char>; _Alloc = std::allocator<std::__cxx11::basic_string<char> >; allocator_type = std::allocator<std::__cxx11::basic_string<char> >]’
./boost/algorithm/string/iter_find.hpp:178:31:   required from ‘SequenceSequenceT& boost::algorithm::iter_split(SequenceSequenceT&, RangeT&, FinderT) [with SequenceSequenceT = std::vector<std::__cxx11::basic_string<char> >; RangeT = std::__cxx11::basic_string<char>; FinderT = detail::token_finderF<detail::is_any_ofF<char> >]’
./boost/algorithm/string/split.hpp:146:50:   required from ‘SequenceSequenceT& boost::algorithm::split(SequenceSequenceT&, RangeT&, PredicateT, token_compress_mode_type) [with SequenceSequenceT = std::vector<std::__cxx11::basic_string<char> >; RangeT = std::__cxx11::basic_string<char>; PredicateT = detail::is_any_ofF<char>]’
libs/thread/src/pthread/thread.cpp:537:29:   required from here
./boost/concept/detail/general.hpp:39:47: warning: ‘this’ pointer is null [-Wnonnull]
   39 |     static void failed() { ((Model*)0)->~Model(); }
      |                            ~~~~~~~~~~~~~~~~~~~^~
./boost/concept/usage.hpp:30:7: note: in a call to non-static member function ‘boost::Convertible<X, Y>::~Convertible() [with X = boost::iterators::random_access_traversal_tag; Y = boost::iterators::incrementable_traversal_tag]’
   30 |       ~model()
      |       ^
./boost/concept_check.hpp:208:5: note: in expansion of macro ‘BOOST_CONCEPT_USAGE’
  208 |     BOOST_CONCEPT_USAGE(Convertible) {
      |     ^~~~~~~~~~~~~~~~~~~
./boost/concept/detail/general.hpp: In instantiation of ‘static void boost::concepts::requirement<boost::concepts::failed************ Model::************>::failed() [with Model = boost::concepts::usage_requirements<boost::range_detail::IncrementableIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > > >]’:
./boost/range/concepts.hpp:136:13:   required from ‘struct boost::range_detail::IncrementableIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >’
./boost/range/concepts.hpp:147:16:   required from ‘struct boost::range_detail::SinglePassIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >’
./boost/concept/detail/has_constraints.hpp:32:62:   required by substitution of ‘template<class Model> boost::concepts::detail::yes boost::concepts::detail::has_constraints_(Model*, wrap_constraints<Model, (& Model::constraints)>*) [with Model = boost::range_detail::SinglePassIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >]’
./boost/concept/detail/has_constraints.hpp:42:5:   required from ‘const bool boost::concepts::not_satisfied<boost::range_detail::SinglePassIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > > >::value’
./boost/concept/detail/has_constraints.hpp:45:51:   required from ‘struct boost::concepts::not_satisfied<boost::range_detail::SinglePassIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > > >’
./boost/concept/detail/general.hpp:51:8:   [ skipping 13 instantiation contexts, use -ftemplate-backtrace-limit=0 to disable ]
./boost/iterator/iterator_facade.hpp:901:3:   required from ‘typename boost::iterators::detail::enable_if_interoperable<Derived1, Derived2, typename boost::mpl::apply2<boost::iterators::detail::always_bool2, Derived1, Derived2>::type>::type boost::iterators::operator!=(const iterator_facade<Derived1, V1, TC1, Reference1, Difference1>&, const iterator_facade<Derived2, V2, TC2, Reference2, Difference2>&) [with Derived1 = transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, use_default, use_default>; V1 = std::__cxx11::basic_string<char>; TC1 = forward_traversal_tag; Reference1 = std::__cxx11::basic_string<char>; Difference1 = long int; Derived2 = transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, use_default, use_default>; V2 = std::__cxx11::basic_string<char>; TC2 = forward_traversal_tag; Reference2 = std::__cxx11::basic_string<char>; Difference2 = long int; typename detail::enable_if_interoperable<Derived1, Derived2, typename boost::mpl::apply2<detail::always_bool2, Derived1, Derived2>::type>::type = bool; typename boost::mpl::apply2<detail::always_bool2, Derived1, Derived2>::type = bool]’
/usr/include/c++/13/bits/stl_vector.h:1671:21:   required from ‘void std::vector<_Tp, _Alloc>::_M_range_initialize(_InputIterator, _InputIterator, std::input_iterator_tag) [with _InputIterator = boost::iterators::transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::iterators::use_default, boost::iterators::use_default>; _Tp = std::__cxx11::basic_string<char>; _Alloc = std::allocator<std::__cxx11::basic_string<char> >]’
/usr/include/c++/13/bits/stl_vector.h:711:23:   required from ‘std::vector<_Tp, _Alloc>::vector(_InputIterator, _InputIterator, const allocator_type&) [with _InputIterator = boost::iterators::transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::iterators::use_default, boost::iterators::use_default>; <template-parameter-2-2> = void; _Tp = std::__cxx11::basic_string<char>; _Alloc = std::allocator<std::__cxx11::basic_string<char> >; allocator_type = std::allocator<std::__cxx11::basic_string<char> >]’
./boost/algorithm/string/iter_find.hpp:178:31:   required from ‘SequenceSequenceT& boost::algorithm::iter_split(SequenceSequenceT&, RangeT&, FinderT) [with SequenceSequenceT = std::vector<std::__cxx11::basic_string<char> >; RangeT = std::__cxx11::basic_string<char>; FinderT = detail::token_finderF<detail::is_any_ofF<char> >]’
./boost/algorithm/string/split.hpp:146:50:   required from ‘SequenceSequenceT& boost::algorithm::split(SequenceSequenceT&, RangeT&, PredicateT, token_compress_mode_type) [with SequenceSequenceT = std::vector<std::__cxx11::basic_string<char> >; RangeT = std::__cxx11::basic_string<char>; PredicateT = detail::is_any_ofF<char>]’
libs/thread/src/pthread/thread.cpp:537:29:   required from here
./boost/concept/detail/general.hpp:39:47: warning: ‘this’ pointer is null [-Wnonnull]
   39 |     static void failed() { ((Model*)0)->~Model(); }
      |                            ~~~~~~~~~~~~~~~~~~~^~
./boost/concept/usage.hpp:16:5: note: in a call to non-static member function ‘boost::concepts::usage_requirements<Model>::~usage_requirements() [with Model = boost::range_detail::IncrementableIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >]’
   16 |     ~usage_requirements() { ((Model*)0)->~Model(); }
      |     ^
./boost/concept/detail/general.hpp: In instantiation of ‘static void boost::concepts::requirement<boost::concepts::failed************ Model::************>::failed() [with Model = boost::concepts::usage_requirements<boost::EqualityComparable<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > > >]’:
./boost/concept_check.hpp:233:5:   required from ‘struct boost::EqualityComparable<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >’
./boost/range/concepts.hpp:147:16:   required from ‘struct boost::range_detail::SinglePassIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >’
./boost/concept/detail/has_constraints.hpp:32:62:   required by substitution of ‘template<class Model> boost::concepts::detail::yes boost::concepts::detail::has_constraints_(Model*, wrap_constraints<Model, (& Model::constraints)>*) [with Model = boost::range_detail::SinglePassIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >]’
./boost/concept/detail/has_constraints.hpp:42:5:   required from ‘const bool boost::concepts::not_satisfied<boost::range_detail::SinglePassIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > > >::value’
./boost/concept/detail/has_constraints.hpp:45:51:   required from ‘struct boost::concepts::not_satisfied<boost::range_detail::SinglePassIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > > >’
./boost/concept/detail/general.hpp:51:8:   [ skipping 13 instantiation contexts, use -ftemplate-backtrace-limit=0 to disable ]
./boost/iterator/iterator_facade.hpp:901:3:   required from ‘typename boost::iterators::detail::enable_if_interoperable<Derived1, Derived2, typename boost::mpl::apply2<boost::iterators::detail::always_bool2, Derived1, Derived2>::type>::type boost::iterators::operator!=(const iterator_facade<Derived1, V1, TC1, Reference1, Difference1>&, const iterator_facade<Derived2, V2, TC2, Reference2, Difference2>&) [with Derived1 = transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, use_default, use_default>; V1 = std::__cxx11::basic_string<char>; TC1 = forward_traversal_tag; Reference1 = std::__cxx11::basic_string<char>; Difference1 = long int; Derived2 = transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, use_default, use_default>; V2 = std::__cxx11::basic_string<char>; TC2 = forward_traversal_tag; Reference2 = std::__cxx11::basic_string<char>; Difference2 = long int; typename detail::enable_if_interoperable<Derived1, Derived2, typename boost::mpl::apply2<detail::always_bool2, Derived1, Derived2>::type>::type = bool; typename boost::mpl::apply2<detail::always_bool2, Derived1, Derived2>::type = bool]’
/usr/include/c++/13/bits/stl_vector.h:1671:21:   required from ‘void std::vector<_Tp, _Alloc>::_M_range_initialize(_InputIterator, _InputIterator, std::input_iterator_tag) [with _InputIterator = boost::iterators::transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::iterators::use_default, boost::iterators::use_default>; _Tp = std::__cxx11::basic_string<char>; _Alloc = std::allocator<std::__cxx11::basic_string<char> >]’
/usr/include/c++/13/bits/stl_vector.h:711:23:   required from ‘std::vector<_Tp, _Alloc>::vector(_InputIterator, _InputIterator, const allocator_type&) [with _InputIterator = boost::iterators::transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::iterators::use_default, boost::iterators::use_default>; <template-parameter-2-2> = void; _Tp = std::__cxx11::basic_string<char>; _Alloc = std::allocator<std::__cxx11::basic_string<char> >; allocator_type = std::allocator<std::__cxx11::basic_string<char> >]’
./boost/algorithm/string/iter_find.hpp:178:31:   required from ‘SequenceSequenceT& boost::algorithm::iter_split(SequenceSequenceT&, RangeT&, FinderT) [with SequenceSequenceT = std::vector<std::__cxx11::basic_string<char> >; RangeT = std::__cxx11::basic_string<char>; FinderT = detail::token_finderF<detail::is_any_ofF<char> >]’
./boost/algorithm/string/split.hpp:146:50:   required from ‘SequenceSequenceT& boost::algorithm::split(SequenceSequenceT&, RangeT&, PredicateT, token_compress_mode_type) [with SequenceSequenceT = std::vector<std::__cxx11::basic_string<char> >; RangeT = std::__cxx11::basic_string<char>; PredicateT = detail::is_any_ofF<char>]’
libs/thread/src/pthread/thread.cpp:537:29:   required from here
./boost/concept/detail/general.hpp:39:47: warning: ‘this’ pointer is null [-Wnonnull]
   39 |     static void failed() { ((Model*)0)->~Model(); }
      |                            ~~~~~~~~~~~~~~~~~~~^~
./boost/concept/usage.hpp:16:5: note: in a call to non-static member function ‘boost::concepts::usage_requirements<Model>::~usage_requirements() [with Model = boost::EqualityComparable<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >]’
   16 |     ~usage_requirements() { ((Model*)0)->~Model(); }
      |     ^
./boost/concept/detail/general.hpp: In instantiation of ‘static void boost::concepts::requirement<boost::concepts::failed************ Model::************>::failed() [with Model = boost::concepts::usage_requirements<boost::Convertible<boost::iterators::random_access_traversal_tag, boost::iterators::single_pass_traversal_tag> >]’:
./boost/concept_check.hpp:208:5:   required from ‘struct boost::Convertible<boost::iterators::random_access_traversal_tag, boost::iterators::single_pass_traversal_tag>’
./boost/concept/detail/has_constraints.hpp:32:62:   required by substitution of ‘template<class Model> boost::concepts::detail::yes boost::concepts::detail::has_constraints_(Model*, wrap_constraints<Model, (& Model::constraints)>*) [with Model = boost::Convertible<boost::iterators::random_access_traversal_tag, boost::iterators::single_pass_traversal_tag>]’
./boost/concept/detail/has_constraints.hpp:42:5:   required from ‘const bool boost::concepts::not_satisfied<boost::Convertible<boost::iterators::random_access_traversal_tag, boost::iterators::single_pass_traversal_tag> >::value’
./boost/concept/detail/has_constraints.hpp:45:51:   required from ‘struct boost::concepts::not_satisfied<boost::Convertible<boost::iterators::random_access_traversal_tag, boost::iterators::single_pass_traversal_tag> >’
./boost/concept/detail/general.hpp:51:8:   required from ‘struct boost::concepts::requirement_<void (*)(boost::Convertible<boost::iterators::random_access_traversal_tag, boost::iterators::single_pass_traversal_tag>)>’
./boost/range/concepts.hpp:152:13:   [ skipping 17 instantiation contexts, use -ftemplate-backtrace-limit=0 to disable ]
./boost/iterator/iterator_facade.hpp:901:3:   required from ‘typename boost::iterators::detail::enable_if_interoperable<Derived1, Derived2, typename boost::mpl::apply2<boost::iterators::detail::always_bool2, Derived1, Derived2>::type>::type boost::iterators::operator!=(const iterator_facade<Derived1, V1, TC1, Reference1, Difference1>&, const iterator_facade<Derived2, V2, TC2, Reference2, Difference2>&) [with Derived1 = transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, use_default, use_default>; V1 = std::__cxx11::basic_string<char>; TC1 = forward_traversal_tag; Reference1 = std::__cxx11::basic_string<char>; Difference1 = long int; Derived2 = transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, use_default, use_default>; V2 = std::__cxx11::basic_string<char>; TC2 = forward_traversal_tag; Reference2 = std::__cxx11::basic_string<char>; Difference2 = long int; typename detail::enable_if_interoperable<Derived1, Derived2, typename boost::mpl::apply2<detail::always_bool2, Derived1, Derived2>::type>::type = bool; typename boost::mpl::apply2<detail::always_bool2, Derived1, Derived2>::type = bool]’
/usr/include/c++/13/bits/stl_vector.h:1671:21:   required from ‘void std::vector<_Tp, _Alloc>::_M_range_initialize(_InputIterator, _InputIterator, std::input_iterator_tag) [with _InputIterator = boost::iterators::transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::iterators::use_default, boost::iterators::use_default>; _Tp = std::__cxx11::basic_string<char>; _Alloc = std::allocator<std::__cxx11::basic_string<char> >]’
/usr/include/c++/13/bits/stl_vector.h:711:23:   required from ‘std::vector<_Tp, _Alloc>::vector(_InputIterator, _InputIterator, const allocator_type&) [with _InputIterator = boost::iterators::transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::iterators::use_default, boost::iterators::use_default>; <template-parameter-2-2> = void; _Tp = std::__cxx11::basic_string<char>; _Alloc = std::allocator<std::__cxx11::basic_string<char> >; allocator_type = std::allocator<std::__cxx11::basic_string<char> >]’
./boost/algorithm/string/iter_find.hpp:178:31:   required from ‘SequenceSequenceT& boost::algorithm::iter_split(SequenceSequenceT&, RangeT&, FinderT) [with SequenceSequenceT = std::vector<std::__cxx11::basic_string<char> >; RangeT = std::__cxx11::basic_string<char>; FinderT = detail::token_finderF<detail::is_any_ofF<char> >]’
./boost/algorithm/string/split.hpp:146:50:   required from ‘SequenceSequenceT& boost::algorithm::split(SequenceSequenceT&, RangeT&, PredicateT, token_compress_mode_type) [with SequenceSequenceT = std::vector<std::__cxx11::basic_string<char> >; RangeT = std::__cxx11::basic_string<char>; PredicateT = detail::is_any_ofF<char>]’
libs/thread/src/pthread/thread.cpp:537:29:   required from here
./boost/concept/detail/general.hpp:39:47: warning: ‘this’ pointer is null [-Wnonnull]
   39 |     static void failed() { ((Model*)0)->~Model(); }
      |                            ~~~~~~~~~~~~~~~~~~~^~
./boost/concept/usage.hpp:16:5: note: in a call to non-static member function ‘boost::concepts::usage_requirements<Model>::~usage_requirements() [with Model = boost::Convertible<boost::iterators::random_access_traversal_tag, boost::iterators::single_pass_traversal_tag>]’
   16 |     ~usage_requirements() { ((Model*)0)->~Model(); }
      |     ^
./boost/concept/detail/general.hpp: In instantiation of ‘static void boost::concepts::requirement<boost::concepts::failed************ Model::************>::failed() [with Model = boost::Convertible<boost::iterators::random_access_traversal_tag, boost::iterators::single_pass_traversal_tag>]’:
./boost/range/concepts.hpp:152:13:   required from ‘struct boost::range_detail::SinglePassIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >’
./boost/concept/detail/has_constraints.hpp:32:62:   required by substitution of ‘template<class Model> boost::concepts::detail::yes boost::concepts::detail::has_constraints_(Model*, wrap_constraints<Model, (& Model::constraints)>*) [with Model = boost::range_detail::SinglePassIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >]’
./boost/concept/detail/has_constraints.hpp:42:5:   required from ‘const bool boost::concepts::not_satisfied<boost::range_detail::SinglePassIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > > >::value’
./boost/concept/detail/has_constraints.hpp:45:51:   required from ‘struct boost::concepts::not_satisfied<boost::range_detail::SinglePassIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > > >’
./boost/concept/detail/general.hpp:51:8:   required from ‘struct boost::concepts::requirement_<void (*)(boost::range_detail::SinglePassIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >)>’
./boost/range/concepts.hpp:278:9:   [ skipping 12 instantiation contexts, use -ftemplate-backtrace-limit=0 to disable ]
./boost/iterator/iterator_facade.hpp:901:3:   required from ‘typename boost::iterators::detail::enable_if_interoperable<Derived1, Derived2, typename boost::mpl::apply2<boost::iterators::detail::always_bool2, Derived1, Derived2>::type>::type boost::iterators::operator!=(const iterator_facade<Derived1, V1, TC1, Reference1, Difference1>&, const iterator_facade<Derived2, V2, TC2, Reference2, Difference2>&) [with Derived1 = transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, use_default, use_default>; V1 = std::__cxx11::basic_string<char>; TC1 = forward_traversal_tag; Reference1 = std::__cxx11::basic_string<char>; Difference1 = long int; Derived2 = transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, use_default, use_default>; V2 = std::__cxx11::basic_string<char>; TC2 = forward_traversal_tag; Reference2 = std::__cxx11::basic_string<char>; Difference2 = long int; typename detail::enable_if_interoperable<Derived1, Derived2, typename boost::mpl::apply2<detail::always_bool2, Derived1, Derived2>::type>::type = bool; typename boost::mpl::apply2<detail::always_bool2, Derived1, Derived2>::type = bool]’
/usr/include/c++/13/bits/stl_vector.h:1671:21:   required from ‘void std::vector<_Tp, _Alloc>::_M_range_initialize(_InputIterator, _InputIterator, std::input_iterator_tag) [with _InputIterator = boost::iterators::transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::iterators::use_default, boost::iterators::use_default>; _Tp = std::__cxx11::basic_string<char>; _Alloc = std::allocator<std::__cxx11::basic_string<char> >]’
/usr/include/c++/13/bits/stl_vector.h:711:23:   required from ‘std::vector<_Tp, _Alloc>::vector(_InputIterator, _InputIterator, const allocator_type&) [with _InputIterator = boost::iterators::transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::iterators::use_default, boost::iterators::use_default>; <template-parameter-2-2> = void; _Tp = std::__cxx11::basic_string<char>; _Alloc = std::allocator<std::__cxx11::basic_string<char> >; allocator_type = std::allocator<std::__cxx11::basic_string<char> >]’
./boost/algorithm/string/iter_find.hpp:178:31:   required from ‘SequenceSequenceT& boost::algorithm::iter_split(SequenceSequenceT&, RangeT&, FinderT) [with SequenceSequenceT = std::vector<std::__cxx11::basic_string<char> >; RangeT = std::__cxx11::basic_string<char>; FinderT = detail::token_finderF<detail::is_any_ofF<char> >]’
./boost/algorithm/string/split.hpp:146:50:   required from ‘SequenceSequenceT& boost::algorithm::split(SequenceSequenceT&, RangeT&, PredicateT, token_compress_mode_type) [with SequenceSequenceT = std::vector<std::__cxx11::basic_string<char> >; RangeT = std::__cxx11::basic_string<char>; PredicateT = detail::is_any_ofF<char>]’
libs/thread/src/pthread/thread.cpp:537:29:   required from here
./boost/concept/detail/general.hpp:39:47: warning: ‘this’ pointer is null [-Wnonnull]
   39 |     static void failed() { ((Model*)0)->~Model(); }
      |                            ~~~~~~~~~~~~~~~~~~~^~
./boost/concept/usage.hpp:30:7: note: in a call to non-static member function ‘boost::Convertible<X, Y>::~Convertible() [with X = boost::iterators::random_access_traversal_tag; Y = boost::iterators::single_pass_traversal_tag]’
   30 |       ~model()
      |       ^
./boost/concept_check.hpp:208:5: note: in expansion of macro ‘BOOST_CONCEPT_USAGE’
  208 |     BOOST_CONCEPT_USAGE(Convertible) {
      |     ^~~~~~~~~~~~~~~~~~~
./boost/concept/detail/general.hpp: In instantiation of ‘static void boost::concepts::requirement<boost::concepts::failed************ Model::************>::failed() [with Model = boost::concepts::usage_requirements<boost::range_detail::SinglePassIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > > >]’:
./boost/range/concepts.hpp:158:13:   required from ‘struct boost::range_detail::SinglePassIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >’
./boost/concept/detail/has_constraints.hpp:32:62:   required by substitution of ‘template<class Model> boost::concepts::detail::yes boost::concepts::detail::has_constraints_(Model*, wrap_constraints<Model, (& Model::constraints)>*) [with Model = boost::range_detail::SinglePassIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >]’
./boost/concept/detail/has_constraints.hpp:42:5:   required from ‘const bool boost::concepts::not_satisfied<boost::range_detail::SinglePassIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > > >::value’
./boost/concept/detail/has_constraints.hpp:45:51:   required from ‘struct boost::concepts::not_satisfied<boost::range_detail::SinglePassIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > > >’
./boost/concept/detail/general.hpp:51:8:   required from ‘struct boost::concepts::requirement_<void (*)(boost::range_detail::SinglePassIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >)>’
./boost/range/concepts.hpp:278:9:   [ skipping 12 instantiation contexts, use -ftemplate-backtrace-limit=0 to disable ]
./boost/iterator/iterator_facade.hpp:901:3:   required from ‘typename boost::iterators::detail::enable_if_interoperable<Derived1, Derived2, typename boost::mpl::apply2<boost::iterators::detail::always_bool2, Derived1, Derived2>::type>::type boost::iterators::operator!=(const iterator_facade<Derived1, V1, TC1, Reference1, Difference1>&, const iterator_facade<Derived2, V2, TC2, Reference2, Difference2>&) [with Derived1 = transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, use_default, use_default>; V1 = std::__cxx11::basic_string<char>; TC1 = forward_traversal_tag; Reference1 = std::__cxx11::basic_string<char>; Difference1 = long int; Derived2 = transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, use_default, use_default>; V2 = std::__cxx11::basic_string<char>; TC2 = forward_traversal_tag; Reference2 = std::__cxx11::basic_string<char>; Difference2 = long int; typename detail::enable_if_interoperable<Derived1, Derived2, typename boost::mpl::apply2<detail::always_bool2, Derived1, Derived2>::type>::type = bool; typename boost::mpl::apply2<detail::always_bool2, Derived1, Derived2>::type = bool]’
/usr/include/c++/13/bits/stl_vector.h:1671:21:   required from ‘void std::vector<_Tp, _Alloc>::_M_range_initialize(_InputIterator, _InputIterator, std::input_iterator_tag) [with _InputIterator = boost::iterators::transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::iterators::use_default, boost::iterators::use_default>; _Tp = std::__cxx11::basic_string<char>; _Alloc = std::allocator<std::__cxx11::basic_string<char> >]’
/usr/include/c++/13/bits/stl_vector.h:711:23:   required from ‘std::vector<_Tp, _Alloc>::vector(_InputIterator, _InputIterator, const allocator_type&) [with _InputIterator = boost::iterators::transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::iterators::use_default, boost::iterators::use_default>; <template-parameter-2-2> = void; _Tp = std::__cxx11::basic_string<char>; _Alloc = std::allocator<std::__cxx11::basic_string<char> >; allocator_type = std::allocator<std::__cxx11::basic_string<char> >]’
./boost/algorithm/string/iter_find.hpp:178:31:   required from ‘SequenceSequenceT& boost::algorithm::iter_split(SequenceSequenceT&, RangeT&, FinderT) [with SequenceSequenceT = std::vector<std::__cxx11::basic_string<char> >; RangeT = std::__cxx11::basic_string<char>; FinderT = detail::token_finderF<detail::is_any_ofF<char> >]’
./boost/algorithm/string/split.hpp:146:50:   required from ‘SequenceSequenceT& boost::algorithm::split(SequenceSequenceT&, RangeT&, PredicateT, token_compress_mode_type) [with SequenceSequenceT = std::vector<std::__cxx11::basic_string<char> >; RangeT = std::__cxx11::basic_string<char>; PredicateT = detail::is_any_ofF<char>]’
libs/thread/src/pthread/thread.cpp:537:29:   required from here
./boost/concept/detail/general.hpp:39:47: warning: ‘this’ pointer is null [-Wnonnull]
   39 |     static void failed() { ((Model*)0)->~Model(); }
      |                            ~~~~~~~~~~~~~~~~~~~^~
./boost/concept/usage.hpp:16:5: note: in a call to non-static member function ‘boost::concepts::usage_requirements<Model>::~usage_requirements() [with Model = boost::range_detail::SinglePassIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >]’
   16 |     ~usage_requirements() { ((Model*)0)->~Model(); }
      |     ^
./boost/concept/detail/general.hpp: In instantiation of ‘static void boost::concepts::requirement<boost::concepts::failed************ Model::************>::failed() [with Model = boost::range_detail::SinglePassIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >]’:
./boost/range/concepts.hpp:278:9:   required from ‘struct boost::SinglePassRangeConcept<const boost::iterator_range<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > > >’
./boost/concept/detail/has_constraints.hpp:32:62:   required by substitution of ‘template<class Model> boost::concepts::detail::yes boost::concepts::detail::has_constraints_(Model*, wrap_constraints<Model, (& Model::constraints)>*) [with Model = boost::SinglePassRangeConcept<const boost::iterator_range<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > > >]’
./boost/concept/detail/has_constraints.hpp:42:5:   required from ‘const bool boost::concepts::not_satisfied<boost::SinglePassRangeConcept<const boost::iterator_range<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > > > >::value’
./boost/concept/detail/has_constraints.hpp:45:51:   required from ‘struct boost::concepts::not_satisfied<boost::SinglePassRangeConcept<const boost::iterator_range<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > > > >’
./boost/concept/detail/general.hpp:51:8:   required from ‘struct boost::concepts::requirement_<void (*)(boost::SinglePassRangeConcept<const boost::iterator_range<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > > >)>’
./boost/range/algorithm/equal.hpp:174:13:   [ skipping 7 instantiation contexts, use -ftemplate-backtrace-limit=0 to disable ]
./boost/iterator/iterator_facade.hpp:901:3:   required from ‘typename boost::iterators::detail::enable_if_interoperable<Derived1, Derived2, typename boost::mpl::apply2<boost::iterators::detail::always_bool2, Derived1, Derived2>::type>::type boost::iterators::operator!=(const iterator_facade<Derived1, V1, TC1, Reference1, Difference1>&, const iterator_facade<Derived2, V2, TC2, Reference2, Difference2>&) [with Derived1 = transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, use_default, use_default>; V1 = std::__cxx11::basic_string<char>; TC1 = forward_traversal_tag; Reference1 = std::__cxx11::basic_string<char>; Difference1 = long int; Derived2 = transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, use_default, use_default>; V2 = std::__cxx11::basic_string<char>; TC2 = forward_traversal_tag; Reference2 = std::__cxx11::basic_string<char>; Difference2 = long int; typename detail::enable_if_interoperable<Derived1, Derived2, typename boost::mpl::apply2<detail::always_bool2, Derived1, Derived2>::type>::type = bool; typename boost::mpl::apply2<detail::always_bool2, Derived1, Derived2>::type = bool]’
/usr/include/c++/13/bits/stl_vector.h:1671:21:   required from ‘void std::vector<_Tp, _Alloc>::_M_range_initialize(_InputIterator, _InputIterator, std::input_iterator_tag) [with _InputIterator = boost::iterators::transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::iterators::use_default, boost::iterators::use_default>; _Tp = std::__cxx11::basic_string<char>; _Alloc = std::allocator<std::__cxx11::basic_string<char> >]’
/usr/include/c++/13/bits/stl_vector.h:711:23:   required from ‘std::vector<_Tp, _Alloc>::vector(_InputIterator, _InputIterator, const allocator_type&) [with _InputIterator = boost::iterators::transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::iterators::use_default, boost::iterators::use_default>; <template-parameter-2-2> = void; _Tp = std::__cxx11::basic_string<char>; _Alloc = std::allocator<std::__cxx11::basic_string<char> >; allocator_type = std::allocator<std::__cxx11::basic_string<char> >]’
./boost/algorithm/string/iter_find.hpp:178:31:   required from ‘SequenceSequenceT& boost::algorithm::iter_split(SequenceSequenceT&, RangeT&, FinderT) [with SequenceSequenceT = std::vector<std::__cxx11::basic_string<char> >; RangeT = std::__cxx11::basic_string<char>; FinderT = detail::token_finderF<detail::is_any_ofF<char> >]’
./boost/algorithm/string/split.hpp:146:50:   required from ‘SequenceSequenceT& boost::algorithm::split(SequenceSequenceT&, RangeT&, PredicateT, token_compress_mode_type) [with SequenceSequenceT = std::vector<std::__cxx11::basic_string<char> >; RangeT = std::__cxx11::basic_string<char>; PredicateT = detail::is_any_ofF<char>]’
libs/thread/src/pthread/thread.cpp:537:29:   required from here
./boost/concept/detail/general.hpp:39:47: warning: ‘this’ pointer is null [-Wnonnull]
   39 |     static void failed() { ((Model*)0)->~Model(); }
      |                            ~~~~~~~~~~~~~~~~~~~^~
./boost/concept/usage.hpp:30:7: note: in a call to non-static member function ‘boost::range_detail::SinglePassIteratorConcept<Iterator>::~SinglePassIteratorConcept() [with Iterator = __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> >]’
   30 |       ~model()
      |       ^
./boost/range/concepts.hpp:158:13: note: in expansion of macro ‘BOOST_CONCEPT_USAGE’
  158 |             BOOST_CONCEPT_USAGE(SinglePassIteratorConcept)
      |             ^~~~~~~~~~~~~~~~~~~
./boost/concept/detail/general.hpp: In instantiation of ‘static void boost::concepts::requirement<boost::concepts::failed************ Model::************>::failed() [with Model = boost::concepts::usage_requirements<boost::SinglePassRangeConcept<const boost::iterator_range<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > > > >]’:
./boost/range/concepts.hpp:284:9:   required from ‘struct boost::SinglePassRangeConcept<const boost::iterator_range<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > > >’
./boost/concept/detail/has_constraints.hpp:32:62:   required by substitution of ‘template<class Model> boost::concepts::detail::yes boost::concepts::detail::has_constraints_(Model*, wrap_constraints<Model, (& Model::constraints)>*) [with Model = boost::SinglePassRangeConcept<const boost::iterator_range<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > > >]’
./boost/concept/detail/has_constraints.hpp:42:5:   required from ‘const bool boost::concepts::not_satisfied<boost::SinglePassRangeConcept<const boost::iterator_range<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > > > >::value’
./boost/concept/detail/has_constraints.hpp:45:51:   required from ‘struct boost::concepts::not_satisfied<boost::SinglePassRangeConcept<const boost::iterator_range<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > > > >’
./boost/concept/detail/general.hpp:51:8:   required from ‘struct boost::concepts::requirement_<void (*)(boost::SinglePassRangeConcept<const boost::iterator_range<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > > >)>’
./boost/range/algorithm/equal.hpp:174:13:   [ skipping 7 instantiation contexts, use -ftemplate-backtrace-limit=0 to disable ]
./boost/iterator/iterator_facade.hpp:901:3:   required from ‘typename boost::iterators::detail::enable_if_interoperable<Derived1, Derived2, typename boost::mpl::apply2<boost::iterators::detail::always_bool2, Derived1, Derived2>::type>::type boost::iterators::operator!=(const iterator_facade<Derived1, V1, TC1, Reference1, Difference1>&, const iterator_facade<Derived2, V2, TC2, Reference2, Difference2>&) [with Derived1 = transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, use_default, use_default>; V1 = std::__cxx11::basic_string<char>; TC1 = forward_traversal_tag; Reference1 = std::__cxx11::basic_string<char>; Difference1 = long int; Derived2 = transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, use_default, use_default>; V2 = std::__cxx11::basic_string<char>; TC2 = forward_traversal_tag; Reference2 = std::__cxx11::basic_string<char>; Difference2 = long int; typename detail::enable_if_interoperable<Derived1, Derived2, typename boost::mpl::apply2<detail::always_bool2, Derived1, Derived2>::type>::type = bool; typename boost::mpl::apply2<detail::always_bool2, Derived1, Derived2>::type = bool]’
/usr/include/c++/13/bits/stl_vector.h:1671:21:   required from ‘void std::vector<_Tp, _Alloc>::_M_range_initialize(_InputIterator, _InputIterator, std::input_iterator_tag) [with _InputIterator = boost::iterators::transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::iterators::use_default, boost::iterators::use_default>; _Tp = std::__cxx11::basic_string<char>; _Alloc = std::allocator<std::__cxx11::basic_string<char> >]’
/usr/include/c++/13/bits/stl_vector.h:711:23:   required from ‘std::vector<_Tp, _Alloc>::vector(_InputIterator, _InputIterator, const allocator_type&) [with _InputIterator = boost::iterators::transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::iterators::use_default, boost::iterators::use_default>; <template-parameter-2-2> = void; _Tp = std::__cxx11::basic_string<char>; _Alloc = std::allocator<std::__cxx11::basic_string<char> >; allocator_type = std::allocator<std::__cxx11::basic_string<char> >]’
./boost/algorithm/string/iter_find.hpp:178:31:   required from ‘SequenceSequenceT& boost::algorithm::iter_split(SequenceSequenceT&, RangeT&, FinderT) [with SequenceSequenceT = std::vector<std::__cxx11::basic_string<char> >; RangeT = std::__cxx11::basic_string<char>; FinderT = detail::token_finderF<detail::is_any_ofF<char> >]’
./boost/algorithm/string/split.hpp:146:50:   required from ‘SequenceSequenceT& boost::algorithm::split(SequenceSequenceT&, RangeT&, PredicateT, token_compress_mode_type) [with SequenceSequenceT = std::vector<std::__cxx11::basic_string<char> >; RangeT = std::__cxx11::basic_string<char>; PredicateT = detail::is_any_ofF<char>]’
libs/thread/src/pthread/thread.cpp:537:29:   required from here
./boost/concept/detail/general.hpp:39:47: warning: ‘this’ pointer is null [-Wnonnull]
   39 |     static void failed() { ((Model*)0)->~Model(); }
      |                            ~~~~~~~~~~~~~~~~~~~^~
./boost/concept/usage.hpp:16:5: note: in a call to non-static member function ‘boost::concepts::usage_requirements<Model>::~usage_requirements() [with Model = boost::SinglePassRangeConcept<const boost::iterator_range<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > > >]’
   16 |     ~usage_requirements() { ((Model*)0)->~Model(); }
      |     ^
./boost/concept/detail/general.hpp: In instantiation of ‘static void boost::concepts::requirement<boost::concepts::failed************ Model::************>::failed() [with Model = boost::SinglePassRangeConcept<const boost::iterator_range<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > > >]’:
./boost/range/algorithm/equal.hpp:174:13:   required from ‘bool boost::range::equal(const SinglePassRange1&, const SinglePassRange2&) [with SinglePassRange1 = boost::iterator_range<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >; SinglePassRange2 = boost::iterator_range<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >]’
./boost/range/iterator_range_core.hpp:646:32:   required from ‘bool boost::operator==(const iterator_range<IteratorT>&, const iterator_range<Iterator2T>&) [with Iterator1T = __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> >; Iterator2T = __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> >]’
./boost/algorithm/string/find_iterator.hpp:333:32:   required from ‘bool boost::algorithm::split_iterator<IteratorT>::equal(const boost::algorithm::split_iterator<IteratorT>&) const [with IteratorT = __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> >]’
./boost/iterator/iterator_facade.hpp:568:26:   required from ‘static bool boost::iterators::iterator_core_access::equal(const Facade1&, const Facade2&, mpl_::true_) [with Facade1 = boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >; Facade2 = boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >; mpl_::true_ = mpl_::bool_<true>]’
./boost/iterator/iterator_facade.hpp:900:3:   required from ‘typename boost::iterators::detail::enable_if_interoperable<Derived1, Derived2, typename boost::mpl::apply2<boost::iterators::detail::always_bool2, Derived1, Derived2>::type>::type boost::iterators::operator==(const iterator_facade<Derived1, V1, TC1, Reference1, Difference1>&, const iterator_facade<Derived2, V2, TC2, Reference2, Difference2>&) [with Derived1 = boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >; V1 = const boost::iterator_range<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >; TC1 = forward_traversal_tag; Reference1 = const boost::iterator_range<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >&; Difference1 = long int; Derived2 = boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >; V2 = const boost::iterator_range<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >; TC2 = forward_traversal_tag; Reference2 = const boost::iterator_range<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >&; Difference2 = long int; typename detail::enable_if_interoperable<Derived1, Derived2, typename boost::mpl::apply2<detail::always_bool2, Derived1, Derived2>::type>::type = bool; typename boost::mpl::apply2<detail::always_bool2, Derived1, Derived2>::type = bool]’
./boost/iterator/iterator_adaptor.hpp:305:29:   [ skipping 2 instantiation contexts, use -ftemplate-backtrace-limit=0 to disable ]
./boost/iterator/iterator_facade.hpp:901:3:   required from ‘typename boost::iterators::detail::enable_if_interoperable<Derived1, Derived2, typename boost::mpl::apply2<boost::iterators::detail::always_bool2, Derived1, Derived2>::type>::type boost::iterators::operator!=(const iterator_facade<Derived1, V1, TC1, Reference1, Difference1>&, const iterator_facade<Derived2, V2, TC2, Reference2, Difference2>&) [with Derived1 = transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, use_default, use_default>; V1 = std::__cxx11::basic_string<char>; TC1 = forward_traversal_tag; Reference1 = std::__cxx11::basic_string<char>; Difference1 = long int; Derived2 = transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, use_default, use_default>; V2 = std::__cxx11::basic_string<char>; TC2 = forward_traversal_tag; Reference2 = std::__cxx11::basic_string<char>; Difference2 = long int; typename detail::enable_if_interoperable<Derived1, Derived2, typename boost::mpl::apply2<detail::always_bool2, Derived1, Derived2>::type>::type = bool; typename boost::mpl::apply2<detail::always_bool2, Derived1, Derived2>::type = bool]’
/usr/include/c++/13/bits/stl_vector.h:1671:21:   required from ‘void std::vector<_Tp, _Alloc>::_M_range_initialize(_InputIterator, _InputIterator, std::input_iterator_tag) [with _InputIterator = boost::iterators::transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::iterators::use_default, boost::iterators::use_default>; _Tp = std::__cxx11::basic_string<char>; _Alloc = std::allocator<std::__cxx11::basic_string<char> >]’
/usr/include/c++/13/bits/stl_vector.h:711:23:   required from ‘std::vector<_Tp, _Alloc>::vector(_InputIterator, _InputIterator, const allocator_type&) [with _InputIterator = boost::iterators::transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::iterators::use_default, boost::iterators::use_default>; <template-parameter-2-2> = void; _Tp = std::__cxx11::basic_string<char>; _Alloc = std::allocator<std::__cxx11::basic_string<char> >; allocator_type = std::allocator<std::__cxx11::basic_string<char> >]’
./boost/algorithm/string/iter_find.hpp:178:31:   required from ‘SequenceSequenceT& boost::algorithm::iter_split(SequenceSequenceT&, RangeT&, FinderT) [with SequenceSequenceT = std::vector<std::__cxx11::basic_string<char> >; RangeT = std::__cxx11::basic_string<char>; FinderT = detail::token_finderF<detail::is_any_ofF<char> >]’
./boost/algorithm/string/split.hpp:146:50:   required from ‘SequenceSequenceT& boost::algorithm::split(SequenceSequenceT&, RangeT&, PredicateT, token_compress_mode_type) [with SequenceSequenceT = std::vector<std::__cxx11::basic_string<char> >; RangeT = std::__cxx11::basic_string<char>; PredicateT = detail::is_any_ofF<char>]’
libs/thread/src/pthread/thread.cpp:537:29:   required from here
./boost/concept/detail/general.hpp:39:47: warning: ‘this’ pointer is null [-Wnonnull]
   39 |     static void failed() { ((Model*)0)->~Model(); }
      |                            ~~~~~~~~~~~~~~~~~~~^~
./boost/concept/usage.hpp:30:7: note: in a call to non-static member function ‘boost::SinglePassRangeConcept<T>::~SinglePassRangeConcept() [with T = const boost::iterator_range<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >]’
   30 |       ~model()
      |       ^
./boost/range/concepts.hpp:284:9: note: in expansion of macro ‘BOOST_CONCEPT_USAGE’
  284 |         BOOST_CONCEPT_USAGE(SinglePassRangeConcept)
      |         ^~~~~~~~~~~~~~~~~~~
./boost/concept/usage.hpp: In instantiation of ‘boost::concepts::usage_requirements<Model>::~usage_requirements() [with Model = boost::CopyConstructible<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >]’:
./boost/concept/detail/general.hpp:39:47:   required from ‘static void boost::concepts::requirement<boost::concepts::failed************ Model::************>::failed() [with Model = boost::concepts::usage_requirements<boost::CopyConstructible<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > > >]’
./boost/concept_check.hpp:167:5:   required from ‘struct boost::CopyConstructible<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >’
./boost/range/concepts.hpp:125:16:   required from ‘struct boost::range_detail::IncrementableIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >’
./boost/range/concepts.hpp:147:16:   required from ‘struct boost::range_detail::SinglePassIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >’
./boost/concept/detail/has_constraints.hpp:32:62:   required by substitution of ‘template<class Model> boost::concepts::detail::yes boost::concepts::detail::has_constraints_(Model*, wrap_constraints<Model, (& Model::constraints)>*) [with Model = boost::range_detail::SinglePassIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >]’
./boost/concept/detail/has_constraints.hpp:42:5:   [ skipping 15 instantiation contexts, use -ftemplate-backtrace-limit=0 to disable ]
./boost/iterator/iterator_facade.hpp:901:3:   required from ‘typename boost::iterators::detail::enable_if_interoperable<Derived1, Derived2, typename boost::mpl::apply2<boost::iterators::detail::always_bool2, Derived1, Derived2>::type>::type boost::iterators::operator!=(const iterator_facade<Derived1, V1, TC1, Reference1, Difference1>&, const iterator_facade<Derived2, V2, TC2, Reference2, Difference2>&) [with Derived1 = transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, use_default, use_default>; V1 = std::__cxx11::basic_string<char>; TC1 = forward_traversal_tag; Reference1 = std::__cxx11::basic_string<char>; Difference1 = long int; Derived2 = transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, use_default, use_default>; V2 = std::__cxx11::basic_string<char>; TC2 = forward_traversal_tag; Reference2 = std::__cxx11::basic_string<char>; Difference2 = long int; typename detail::enable_if_interoperable<Derived1, Derived2, typename boost::mpl::apply2<detail::always_bool2, Derived1, Derived2>::type>::type = bool; typename boost::mpl::apply2<detail::always_bool2, Derived1, Derived2>::type = bool]’
/usr/include/c++/13/bits/stl_vector.h:1671:21:   required from ‘void std::vector<_Tp, _Alloc>::_M_range_initialize(_InputIterator, _InputIterator, std::input_iterator_tag) [with _InputIterator = boost::iterators::transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::iterators::use_default, boost::iterators::use_default>; _Tp = std::__cxx11::basic_string<char>; _Alloc = std::allocator<std::__cxx11::basic_string<char> >]’
/usr/include/c++/13/bits/stl_vector.h:711:23:   required from ‘std::vector<_Tp, _Alloc>::vector(_InputIterator, _InputIterator, const allocator_type&) [with _InputIterator = boost::iterators::transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::iterators::use_default, boost::iterators::use_default>; <template-parameter-2-2> = void; _Tp = std::__cxx11::basic_string<char>; _Alloc = std::allocator<std::__cxx11::basic_string<char> >; allocator_type = std::allocator<std::__cxx11::basic_string<char> >]’
./boost/algorithm/string/iter_find.hpp:178:31:   required from ‘SequenceSequenceT& boost::algorithm::iter_split(SequenceSequenceT&, RangeT&, FinderT) [with SequenceSequenceT = std::vector<std::__cxx11::basic_string<char> >; RangeT = std::__cxx11::basic_string<char>; FinderT = detail::token_finderF<detail::is_any_ofF<char> >]’
./boost/algorithm/string/split.hpp:146:50:   required from ‘SequenceSequenceT& boost::algorithm::split(SequenceSequenceT&, RangeT&, PredicateT, token_compress_mode_type) [with SequenceSequenceT = std::vector<std::__cxx11::basic_string<char> >; RangeT = std::__cxx11::basic_string<char>; PredicateT = detail::is_any_ofF<char>]’
libs/thread/src/pthread/thread.cpp:537:29:   required from here
./boost/concept/usage.hpp:16:48: warning: ‘this’ pointer is null [-Wnonnull]
   16 |     ~usage_requirements() { ((Model*)0)->~Model(); }
      |                             ~~~~~~~~~~~~~~~~~~~^~
./boost/concept/usage.hpp:30:7: note: in a call to non-static member function ‘boost::CopyConstructible<TT>::~CopyConstructible() [with TT = __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> >]’
   30 |       ~model()
      |       ^
./boost/concept_check.hpp:167:5: note: in expansion of macro ‘BOOST_CONCEPT_USAGE’
  167 |     BOOST_CONCEPT_USAGE(CopyConstructible) {
      |     ^~~~~~~~~~~~~~~~~~~
./boost/concept/usage.hpp: In instantiation of ‘boost::concepts::usage_requirements<Model>::~usage_requirements() [with Model = boost::Convertible<boost::iterators::random_access_traversal_tag, boost::iterators::incrementable_traversal_tag>]’:
./boost/concept/detail/general.hpp:39:47:   required from ‘static void boost::concepts::requirement<boost::concepts::failed************ Model::************>::failed() [with Model = boost::concepts::usage_requirements<boost::Convertible<boost::iterators::random_access_traversal_tag, boost::iterators::incrementable_traversal_tag> >]’
./boost/concept_check.hpp:208:5:   required from ‘struct boost::Convertible<boost::iterators::random_access_traversal_tag, boost::iterators::incrementable_traversal_tag>’
./boost/concept/detail/has_constraints.hpp:32:62:   required by substitution of ‘template<class Model> boost::concepts::detail::yes boost::concepts::detail::has_constraints_(Model*, wrap_constraints<Model, (& Model::constraints)>*) [with Model = boost::Convertible<boost::iterators::random_access_traversal_tag, boost::iterators::incrementable_traversal_tag>]’
./boost/concept/detail/has_constraints.hpp:42:5:   required from ‘const bool boost::concepts::not_satisfied<boost::Convertible<boost::iterators::random_access_traversal_tag, boost::iterators::incrementable_traversal_tag> >::value’
./boost/concept/detail/has_constraints.hpp:45:51:   required from ‘struct boost::concepts::not_satisfied<boost::Convertible<boost::iterators::random_access_traversal_tag, boost::iterators::incrementable_traversal_tag> >’
./boost/concept/detail/general.hpp:51:8:   [ skipping 19 instantiation contexts, use -ftemplate-backtrace-limit=0 to disable ]
./boost/iterator/iterator_facade.hpp:901:3:   required from ‘typename boost::iterators::detail::enable_if_interoperable<Derived1, Derived2, typename boost::mpl::apply2<boost::iterators::detail::always_bool2, Derived1, Derived2>::type>::type boost::iterators::operator!=(const iterator_facade<Derived1, V1, TC1, Reference1, Difference1>&, const iterator_facade<Derived2, V2, TC2, Reference2, Difference2>&) [with Derived1 = transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, use_default, use_default>; V1 = std::__cxx11::basic_string<char>; TC1 = forward_traversal_tag; Reference1 = std::__cxx11::basic_string<char>; Difference1 = long int; Derived2 = transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, use_default, use_default>; V2 = std::__cxx11::basic_string<char>; TC2 = forward_traversal_tag; Reference2 = std::__cxx11::basic_string<char>; Difference2 = long int; typename detail::enable_if_interoperable<Derived1, Derived2, typename boost::mpl::apply2<detail::always_bool2, Derived1, Derived2>::type>::type = bool; typename boost::mpl::apply2<detail::always_bool2, Derived1, Derived2>::type = bool]’
/usr/include/c++/13/bits/stl_vector.h:1671:21:   required from ‘void std::vector<_Tp, _Alloc>::_M_range_initialize(_InputIterator, _InputIterator, std::input_iterator_tag) [with _InputIterator = boost::iterators::transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::iterators::use_default, boost::iterators::use_default>; _Tp = std::__cxx11::basic_string<char>; _Alloc = std::allocator<std::__cxx11::basic_string<char> >]’
/usr/include/c++/13/bits/stl_vector.h:711:23:   required from ‘std::vector<_Tp, _Alloc>::vector(_InputIterator, _InputIterator, const allocator_type&) [with _InputIterator = boost::iterators::transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::iterators::use_default, boost::iterators::use_default>; <template-parameter-2-2> = void; _Tp = std::__cxx11::basic_string<char>; _Alloc = std::allocator<std::__cxx11::basic_string<char> >; allocator_type = std::allocator<std::__cxx11::basic_string<char> >]’
./boost/algorithm/string/iter_find.hpp:178:31:   required from ‘SequenceSequenceT& boost::algorithm::iter_split(SequenceSequenceT&, RangeT&, FinderT) [with SequenceSequenceT = std::vector<std::__cxx11::basic_string<char> >; RangeT = std::__cxx11::basic_string<char>; FinderT = detail::token_finderF<detail::is_any_ofF<char> >]’
./boost/algorithm/string/split.hpp:146:50:   required from ‘SequenceSequenceT& boost::algorithm::split(SequenceSequenceT&, RangeT&, PredicateT, token_compress_mode_type) [with SequenceSequenceT = std::vector<std::__cxx11::basic_string<char> >; RangeT = std::__cxx11::basic_string<char>; PredicateT = detail::is_any_ofF<char>]’
libs/thread/src/pthread/thread.cpp:537:29:   required from here
./boost/concept/usage.hpp:16:48: warning: ‘this’ pointer is null [-Wnonnull]
   16 |     ~usage_requirements() { ((Model*)0)->~Model(); }
      |                             ~~~~~~~~~~~~~~~~~~~^~
./boost/concept/usage.hpp:30:7: note: in a call to non-static member function ‘boost::Convertible<X, Y>::~Convertible() [with X = boost::iterators::random_access_traversal_tag; Y = boost::iterators::incrementable_traversal_tag]’
   30 |       ~model()
      |       ^
./boost/concept_check.hpp:208:5: note: in expansion of macro ‘BOOST_CONCEPT_USAGE’
  208 |     BOOST_CONCEPT_USAGE(Convertible) {
      |     ^~~~~~~~~~~~~~~~~~~
./boost/concept/usage.hpp: In instantiation of ‘boost::concepts::usage_requirements<Model>::~usage_requirements() [with Model = boost::range_detail::IncrementableIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >]’:
./boost/concept/detail/general.hpp:39:47:   required from ‘static void boost::concepts::requirement<boost::concepts::failed************ Model::************>::failed() [with Model = boost::concepts::usage_requirements<boost::range_detail::IncrementableIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > > >]’
./boost/range/concepts.hpp:136:13:   required from ‘struct boost::range_detail::IncrementableIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >’
./boost/range/concepts.hpp:147:16:   required from ‘struct boost::range_detail::SinglePassIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >’
./boost/concept/detail/has_constraints.hpp:32:62:   required by substitution of ‘template<class Model> boost::concepts::detail::yes boost::concepts::detail::has_constraints_(Model*, wrap_constraints<Model, (& Model::constraints)>*) [with Model = boost::range_detail::SinglePassIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >]’
./boost/concept/detail/has_constraints.hpp:42:5:   required from ‘const bool boost::concepts::not_satisfied<boost::range_detail::SinglePassIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > > >::value’
./boost/concept/detail/has_constraints.hpp:45:51:   [ skipping 14 instantiation contexts, use -ftemplate-backtrace-limit=0 to disable ]
./boost/iterator/iterator_facade.hpp:901:3:   required from ‘typename boost::iterators::detail::enable_if_interoperable<Derived1, Derived2, typename boost::mpl::apply2<boost::iterators::detail::always_bool2, Derived1, Derived2>::type>::type boost::iterators::operator!=(const iterator_facade<Derived1, V1, TC1, Reference1, Difference1>&, const iterator_facade<Derived2, V2, TC2, Reference2, Difference2>&) [with Derived1 = transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, use_default, use_default>; V1 = std::__cxx11::basic_string<char>; TC1 = forward_traversal_tag; Reference1 = std::__cxx11::basic_string<char>; Difference1 = long int; Derived2 = transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, use_default, use_default>; V2 = std::__cxx11::basic_string<char>; TC2 = forward_traversal_tag; Reference2 = std::__cxx11::basic_string<char>; Difference2 = long int; typename detail::enable_if_interoperable<Derived1, Derived2, typename boost::mpl::apply2<detail::always_bool2, Derived1, Derived2>::type>::type = bool; typename boost::mpl::apply2<detail::always_bool2, Derived1, Derived2>::type = bool]’
/usr/include/c++/13/bits/stl_vector.h:1671:21:   required from ‘void std::vector<_Tp, _Alloc>::_M_range_initialize(_InputIterator, _InputIterator, std::input_iterator_tag) [with _InputIterator = boost::iterators::transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::iterators::use_default, boost::iterators::use_default>; _Tp = std::__cxx11::basic_string<char>; _Alloc = std::allocator<std::__cxx11::basic_string<char> >]’
/usr/include/c++/13/bits/stl_vector.h:711:23:   required from ‘std::vector<_Tp, _Alloc>::vector(_InputIterator, _InputIterator, const allocator_type&) [with _InputIterator = boost::iterators::transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::iterators::use_default, boost::iterators::use_default>; <template-parameter-2-2> = void; _Tp = std::__cxx11::basic_string<char>; _Alloc = std::allocator<std::__cxx11::basic_string<char> >; allocator_type = std::allocator<std::__cxx11::basic_string<char> >]’
./boost/algorithm/string/iter_find.hpp:178:31:   required from ‘SequenceSequenceT& boost::algorithm::iter_split(SequenceSequenceT&, RangeT&, FinderT) [with SequenceSequenceT = std::vector<std::__cxx11::basic_string<char> >; RangeT = std::__cxx11::basic_string<char>; FinderT = detail::token_finderF<detail::is_any_ofF<char> >]’
./boost/algorithm/string/split.hpp:146:50:   required from ‘SequenceSequenceT& boost::algorithm::split(SequenceSequenceT&, RangeT&, PredicateT, token_compress_mode_type) [with SequenceSequenceT = std::vector<std::__cxx11::basic_string<char> >; RangeT = std::__cxx11::basic_string<char>; PredicateT = detail::is_any_ofF<char>]’
libs/thread/src/pthread/thread.cpp:537:29:   required from here
./boost/concept/usage.hpp:16:48: warning: ‘this’ pointer is null [-Wnonnull]
   16 |     ~usage_requirements() { ((Model*)0)->~Model(); }
      |                             ~~~~~~~~~~~~~~~~~~~^~
./boost/concept/usage.hpp:30:7: note: in a call to non-static member function ‘boost::range_detail::IncrementableIteratorConcept<Iterator>::~IncrementableIteratorConcept() [with Iterator = __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> >]’
   30 |       ~model()
      |       ^
./boost/range/concepts.hpp:136:13: note: in expansion of macro ‘BOOST_CONCEPT_USAGE’
  136 |             BOOST_CONCEPT_USAGE(IncrementableIteratorConcept)
      |             ^~~~~~~~~~~~~~~~~~~
./boost/concept/usage.hpp: In instantiation of ‘boost::concepts::usage_requirements<Model>::~usage_requirements() [with Model = boost::EqualityComparable<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >]’:
./boost/concept/detail/general.hpp:39:47:   required from ‘static void boost::concepts::requirement<boost::concepts::failed************ Model::************>::failed() [with Model = boost::concepts::usage_requirements<boost::EqualityComparable<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > > >]’
./boost/concept_check.hpp:233:5:   required from ‘struct boost::EqualityComparable<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >’
./boost/range/concepts.hpp:147:16:   required from ‘struct boost::range_detail::SinglePassIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >’
./boost/concept/detail/has_constraints.hpp:32:62:   required by substitution of ‘template<class Model> boost::concepts::detail::yes boost::concepts::detail::has_constraints_(Model*, wrap_constraints<Model, (& Model::constraints)>*) [with Model = boost::range_detail::SinglePassIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >]’
./boost/concept/detail/has_constraints.hpp:42:5:   required from ‘const bool boost::concepts::not_satisfied<boost::range_detail::SinglePassIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > > >::value’
./boost/concept/detail/has_constraints.hpp:45:51:   [ skipping 14 instantiation contexts, use -ftemplate-backtrace-limit=0 to disable ]
./boost/iterator/iterator_facade.hpp:901:3:   required from ‘typename boost::iterators::detail::enable_if_interoperable<Derived1, Derived2, typename boost::mpl::apply2<boost::iterators::detail::always_bool2, Derived1, Derived2>::type>::type boost::iterators::operator!=(const iterator_facade<Derived1, V1, TC1, Reference1, Difference1>&, const iterator_facade<Derived2, V2, TC2, Reference2, Difference2>&) [with Derived1 = transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, use_default, use_default>; V1 = std::__cxx11::basic_string<char>; TC1 = forward_traversal_tag; Reference1 = std::__cxx11::basic_string<char>; Difference1 = long int; Derived2 = transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, use_default, use_default>; V2 = std::__cxx11::basic_string<char>; TC2 = forward_traversal_tag; Reference2 = std::__cxx11::basic_string<char>; Difference2 = long int; typename detail::enable_if_interoperable<Derived1, Derived2, typename boost::mpl::apply2<detail::always_bool2, Derived1, Derived2>::type>::type = bool; typename boost::mpl::apply2<detail::always_bool2, Derived1, Derived2>::type = bool]’
/usr/include/c++/13/bits/stl_vector.h:1671:21:   required from ‘void std::vector<_Tp, _Alloc>::_M_range_initialize(_InputIterator, _InputIterator, std::input_iterator_tag) [with _InputIterator = boost::iterators::transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::iterators::use_default, boost::iterators::use_default>; _Tp = std::__cxx11::basic_string<char>; _Alloc = std::allocator<std::__cxx11::basic_string<char> >]’
/usr/include/c++/13/bits/stl_vector.h:711:23:   required from ‘std::vector<_Tp, _Alloc>::vector(_InputIterator, _InputIterator, const allocator_type&) [with _InputIterator = boost::iterators::transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::iterators::use_default, boost::iterators::use_default>; <template-parameter-2-2> = void; _Tp = std::__cxx11::basic_string<char>; _Alloc = std::allocator<std::__cxx11::basic_string<char> >; allocator_type = std::allocator<std::__cxx11::basic_string<char> >]’
./boost/algorithm/string/iter_find.hpp:178:31:   required from ‘SequenceSequenceT& boost::algorithm::iter_split(SequenceSequenceT&, RangeT&, FinderT) [with SequenceSequenceT = std::vector<std::__cxx11::basic_string<char> >; RangeT = std::__cxx11::basic_string<char>; FinderT = detail::token_finderF<detail::is_any_ofF<char> >]’
./boost/algorithm/string/split.hpp:146:50:   required from ‘SequenceSequenceT& boost::algorithm::split(SequenceSequenceT&, RangeT&, PredicateT, token_compress_mode_type) [with SequenceSequenceT = std::vector<std::__cxx11::basic_string<char> >; RangeT = std::__cxx11::basic_string<char>; PredicateT = detail::is_any_ofF<char>]’
libs/thread/src/pthread/thread.cpp:537:29:   required from here
./boost/concept/usage.hpp:16:48: warning: ‘this’ pointer is null [-Wnonnull]
   16 |     ~usage_requirements() { ((Model*)0)->~Model(); }
      |                             ~~~~~~~~~~~~~~~~~~~^~
./boost/concept/usage.hpp:30:7: note: in a call to non-static member function ‘boost::EqualityComparable<TT>::~EqualityComparable() [with TT = __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> >]’
   30 |       ~model()
      |       ^
./boost/concept_check.hpp:233:5: note: in expansion of macro ‘BOOST_CONCEPT_USAGE’
  233 |     BOOST_CONCEPT_USAGE(EqualityComparable) {
      |     ^~~~~~~~~~~~~~~~~~~
./boost/concept/usage.hpp: In instantiation of ‘boost::concepts::usage_requirements<Model>::~usage_requirements() [with Model = boost::Convertible<boost::iterators::random_access_traversal_tag, boost::iterators::single_pass_traversal_tag>]’:
./boost/concept/detail/general.hpp:39:47:   required from ‘static void boost::concepts::requirement<boost::concepts::failed************ Model::************>::failed() [with Model = boost::concepts::usage_requirements<boost::Convertible<boost::iterators::random_access_traversal_tag, boost::iterators::single_pass_traversal_tag> >]’
./boost/concept_check.hpp:208:5:   required from ‘struct boost::Convertible<boost::iterators::random_access_traversal_tag, boost::iterators::single_pass_traversal_tag>’
./boost/concept/detail/has_constraints.hpp:32:62:   required by substitution of ‘template<class Model> boost::concepts::detail::yes boost::concepts::detail::has_constraints_(Model*, wrap_constraints<Model, (& Model::constraints)>*) [with Model = boost::Convertible<boost::iterators::random_access_traversal_tag, boost::iterators::single_pass_traversal_tag>]’
./boost/concept/detail/has_constraints.hpp:42:5:   required from ‘const bool boost::concepts::not_satisfied<boost::Convertible<boost::iterators::random_access_traversal_tag, boost::iterators::single_pass_traversal_tag> >::value’
./boost/concept/detail/has_constraints.hpp:45:51:   required from ‘struct boost::concepts::not_satisfied<boost::Convertible<boost::iterators::random_access_traversal_tag, boost::iterators::single_pass_traversal_tag> >’
./boost/concept/detail/general.hpp:51:8:   [ skipping 18 instantiation contexts, use -ftemplate-backtrace-limit=0 to disable ]
./boost/iterator/iterator_facade.hpp:901:3:   required from ‘typename boost::iterators::detail::enable_if_interoperable<Derived1, Derived2, typename boost::mpl::apply2<boost::iterators::detail::always_bool2, Derived1, Derived2>::type>::type boost::iterators::operator!=(const iterator_facade<Derived1, V1, TC1, Reference1, Difference1>&, const iterator_facade<Derived2, V2, TC2, Reference2, Difference2>&) [with Derived1 = transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, use_default, use_default>; V1 = std::__cxx11::basic_string<char>; TC1 = forward_traversal_tag; Reference1 = std::__cxx11::basic_string<char>; Difference1 = long int; Derived2 = transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, use_default, use_default>; V2 = std::__cxx11::basic_string<char>; TC2 = forward_traversal_tag; Reference2 = std::__cxx11::basic_string<char>; Difference2 = long int; typename detail::enable_if_interoperable<Derived1, Derived2, typename boost::mpl::apply2<detail::always_bool2, Derived1, Derived2>::type>::type = bool; typename boost::mpl::apply2<detail::always_bool2, Derived1, Derived2>::type = bool]’
/usr/include/c++/13/bits/stl_vector.h:1671:21:   required from ‘void std::vector<_Tp, _Alloc>::_M_range_initialize(_InputIterator, _InputIterator, std::input_iterator_tag) [with _InputIterator = boost::iterators::transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::iterators::use_default, boost::iterators::use_default>; _Tp = std::__cxx11::basic_string<char>; _Alloc = std::allocator<std::__cxx11::basic_string<char> >]’
/usr/include/c++/13/bits/stl_vector.h:711:23:   required from ‘std::vector<_Tp, _Alloc>::vector(_InputIterator, _InputIterator, const allocator_type&) [with _InputIterator = boost::iterators::transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::iterators::use_default, boost::iterators::use_default>; <template-parameter-2-2> = void; _Tp = std::__cxx11::basic_string<char>; _Alloc = std::allocator<std::__cxx11::basic_string<char> >; allocator_type = std::allocator<std::__cxx11::basic_string<char> >]’
./boost/algorithm/string/iter_find.hpp:178:31:   required from ‘SequenceSequenceT& boost::algorithm::iter_split(SequenceSequenceT&, RangeT&, FinderT) [with SequenceSequenceT = std::vector<std::__cxx11::basic_string<char> >; RangeT = std::__cxx11::basic_string<char>; FinderT = detail::token_finderF<detail::is_any_ofF<char> >]’
./boost/algorithm/string/split.hpp:146:50:   required from ‘SequenceSequenceT& boost::algorithm::split(SequenceSequenceT&, RangeT&, PredicateT, token_compress_mode_type) [with SequenceSequenceT = std::vector<std::__cxx11::basic_string<char> >; RangeT = std::__cxx11::basic_string<char>; PredicateT = detail::is_any_ofF<char>]’
libs/thread/src/pthread/thread.cpp:537:29:   required from here
./boost/concept/usage.hpp:16:48: warning: ‘this’ pointer is null [-Wnonnull]
   16 |     ~usage_requirements() { ((Model*)0)->~Model(); }
      |                             ~~~~~~~~~~~~~~~~~~~^~
./boost/concept/usage.hpp:30:7: note: in a call to non-static member function ‘boost::Convertible<X, Y>::~Convertible() [with X = boost::iterators::random_access_traversal_tag; Y = boost::iterators::single_pass_traversal_tag]’
   30 |       ~model()
      |       ^
./boost/concept_check.hpp:208:5: note: in expansion of macro ‘BOOST_CONCEPT_USAGE’
  208 |     BOOST_CONCEPT_USAGE(Convertible) {
      |     ^~~~~~~~~~~~~~~~~~~
./boost/concept/usage.hpp: In instantiation of ‘boost::concepts::usage_requirements<Model>::~usage_requirements() [with Model = boost::range_detail::SinglePassIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >]’:
./boost/concept/detail/general.hpp:39:47:   required from ‘static void boost::concepts::requirement<boost::concepts::failed************ Model::************>::failed() [with Model = boost::concepts::usage_requirements<boost::range_detail::SinglePassIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > > >]’
./boost/range/concepts.hpp:158:13:   required from ‘struct boost::range_detail::SinglePassIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >’
./boost/concept/detail/has_constraints.hpp:32:62:   required by substitution of ‘template<class Model> boost::concepts::detail::yes boost::concepts::detail::has_constraints_(Model*, wrap_constraints<Model, (& Model::constraints)>*) [with Model = boost::range_detail::SinglePassIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >]’
./boost/concept/detail/has_constraints.hpp:42:5:   required from ‘const bool boost::concepts::not_satisfied<boost::range_detail::SinglePassIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > > >::value’
./boost/concept/detail/has_constraints.hpp:45:51:   required from ‘struct boost::concepts::not_satisfied<boost::range_detail::SinglePassIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > > >’
./boost/concept/detail/general.hpp:51:8:   [ skipping 13 instantiation contexts, use -ftemplate-backtrace-limit=0 to disable ]
./boost/iterator/iterator_facade.hpp:901:3:   required from ‘typename boost::iterators::detail::enable_if_interoperable<Derived1, Derived2, typename boost::mpl::apply2<boost::iterators::detail::always_bool2, Derived1, Derived2>::type>::type boost::iterators::operator!=(const iterator_facade<Derived1, V1, TC1, Reference1, Difference1>&, const iterator_facade<Derived2, V2, TC2, Reference2, Difference2>&) [with Derived1 = transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, use_default, use_default>; V1 = std::__cxx11::basic_string<char>; TC1 = forward_traversal_tag; Reference1 = std::__cxx11::basic_string<char>; Difference1 = long int; Derived2 = transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, use_default, use_default>; V2 = std::__cxx11::basic_string<char>; TC2 = forward_traversal_tag; Reference2 = std::__cxx11::basic_string<char>; Difference2 = long int; typename detail::enable_if_interoperable<Derived1, Derived2, typename boost::mpl::apply2<detail::always_bool2, Derived1, Derived2>::type>::type = bool; typename boost::mpl::apply2<detail::always_bool2, Derived1, Derived2>::type = bool]’
/usr/include/c++/13/bits/stl_vector.h:1671:21:   required from ‘void std::vector<_Tp, _Alloc>::_M_range_initialize(_InputIterator, _InputIterator, std::input_iterator_tag) [with _InputIterator = boost::iterators::transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::iterators::use_default, boost::iterators::use_default>; _Tp = std::__cxx11::basic_string<char>; _Alloc = std::allocator<std::__cxx11::basic_string<char> >]’
/usr/include/c++/13/bits/stl_vector.h:711:23:   required from ‘std::vector<_Tp, _Alloc>::vector(_InputIterator, _InputIterator, const allocator_type&) [with _InputIterator = boost::iterators::transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::iterators::use_default, boost::iterators::use_default>; <template-parameter-2-2> = void; _Tp = std::__cxx11::basic_string<char>; _Alloc = std::allocator<std::__cxx11::basic_string<char> >; allocator_type = std::allocator<std::__cxx11::basic_string<char> >]’
./boost/algorithm/string/iter_find.hpp:178:31:   required from ‘SequenceSequenceT& boost::algorithm::iter_split(SequenceSequenceT&, RangeT&, FinderT) [with SequenceSequenceT = std::vector<std::__cxx11::basic_string<char> >; RangeT = std::__cxx11::basic_string<char>; FinderT = detail::token_finderF<detail::is_any_ofF<char> >]’
./boost/algorithm/string/split.hpp:146:50:   required from ‘SequenceSequenceT& boost::algorithm::split(SequenceSequenceT&, RangeT&, PredicateT, token_compress_mode_type) [with SequenceSequenceT = std::vector<std::__cxx11::basic_string<char> >; RangeT = std::__cxx11::basic_string<char>; PredicateT = detail::is_any_ofF<char>]’
libs/thread/src/pthread/thread.cpp:537:29:   required from here
./boost/concept/usage.hpp:16:48: warning: ‘this’ pointer is null [-Wnonnull]
   16 |     ~usage_requirements() { ((Model*)0)->~Model(); }
      |                             ~~~~~~~~~~~~~~~~~~~^~
./boost/concept/usage.hpp:30:7: note: in a call to non-static member function ‘boost::range_detail::SinglePassIteratorConcept<Iterator>::~SinglePassIteratorConcept() [with Iterator = __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> >]’
   30 |       ~model()
      |       ^
./boost/range/concepts.hpp:158:13: note: in expansion of macro ‘BOOST_CONCEPT_USAGE’
  158 |             BOOST_CONCEPT_USAGE(SinglePassIteratorConcept)
      |             ^~~~~~~~~~~~~~~~~~~
./boost/concept/usage.hpp: In instantiation of ‘boost::concepts::usage_requirements<Model>::~usage_requirements() [with Model = boost::SinglePassRangeConcept<const boost::iterator_range<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > > >]’:
./boost/concept/detail/general.hpp:39:47:   required from ‘static void boost::concepts::requirement<boost::concepts::failed************ Model::************>::failed() [with Model = boost::concepts::usage_requirements<boost::SinglePassRangeConcept<const boost::iterator_range<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > > > >]’
./boost/range/concepts.hpp:284:9:   required from ‘struct boost::SinglePassRangeConcept<const boost::iterator_range<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > > >’
./boost/concept/detail/has_constraints.hpp:32:62:   required by substitution of ‘template<class Model> boost::concepts::detail::yes boost::concepts::detail::has_constraints_(Model*, wrap_constraints<Model, (& Model::constraints)>*) [with Model = boost::SinglePassRangeConcept<const boost::iterator_range<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > > >]’
./boost/concept/detail/has_constraints.hpp:42:5:   required from ‘const bool boost::concepts::not_satisfied<boost::SinglePassRangeConcept<const boost::iterator_range<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > > > >::value’
./boost/concept/detail/has_constraints.hpp:45:51:   required from ‘struct boost::concepts::not_satisfied<boost::SinglePassRangeConcept<const boost::iterator_range<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > > > >’
./boost/concept/detail/general.hpp:51:8:   [ skipping 8 instantiation contexts, use -ftemplate-backtrace-limit=0 to disable ]
./boost/iterator/iterator_facade.hpp:901:3:   required from ‘typename boost::iterators::detail::enable_if_interoperable<Derived1, Derived2, typename boost::mpl::apply2<boost::iterators::detail::always_bool2, Derived1, Derived2>::type>::type boost::iterators::operator!=(const iterator_facade<Derived1, V1, TC1, Reference1, Difference1>&, const iterator_facade<Derived2, V2, TC2, Reference2, Difference2>&) [with Derived1 = transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, use_default, use_default>; V1 = std::__cxx11::basic_string<char>; TC1 = forward_traversal_tag; Reference1 = std::__cxx11::basic_string<char>; Difference1 = long int; Derived2 = transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, use_default, use_default>; V2 = std::__cxx11::basic_string<char>; TC2 = forward_traversal_tag; Reference2 = std::__cxx11::basic_string<char>; Difference2 = long int; typename detail::enable_if_interoperable<Derived1, Derived2, typename boost::mpl::apply2<detail::always_bool2, Derived1, Derived2>::type>::type = bool; typename boost::mpl::apply2<detail::always_bool2, Derived1, Derived2>::type = bool]’
/usr/include/c++/13/bits/stl_vector.h:1671:21:   required from ‘void std::vector<_Tp, _Alloc>::_M_range_initialize(_InputIterator, _InputIterator, std::input_iterator_tag) [with _InputIterator = boost::iterators::transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::iterators::use_default, boost::iterators::use_default>; _Tp = std::__cxx11::basic_string<char>; _Alloc = std::allocator<std::__cxx11::basic_string<char> >]’
/usr/include/c++/13/bits/stl_vector.h:711:23:   required from ‘std::vector<_Tp, _Alloc>::vector(_InputIterator, _InputIterator, const allocator_type&) [with _InputIterator = boost::iterators::transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::iterators::use_default, boost::iterators::use_default>; <template-parameter-2-2> = void; _Tp = std::__cxx11::basic_string<char>; _Alloc = std::allocator<std::__cxx11::basic_string<char> >; allocator_type = std::allocator<std::__cxx11::basic_string<char> >]’
./boost/algorithm/string/iter_find.hpp:178:31:   required from ‘SequenceSequenceT& boost::algorithm::iter_split(SequenceSequenceT&, RangeT&, FinderT) [with SequenceSequenceT = std::vector<std::__cxx11::basic_string<char> >; RangeT = std::__cxx11::basic_string<char>; FinderT = detail::token_finderF<detail::is_any_ofF<char> >]’
./boost/algorithm/string/split.hpp:146:50:   required from ‘SequenceSequenceT& boost::algorithm::split(SequenceSequenceT&, RangeT&, PredicateT, token_compress_mode_type) [with SequenceSequenceT = std::vector<std::__cxx11::basic_string<char> >; RangeT = std::__cxx11::basic_string<char>; PredicateT = detail::is_any_ofF<char>]’
libs/thread/src/pthread/thread.cpp:537:29:   required from here
./boost/concept/usage.hpp:16:48: warning: ‘this’ pointer is null [-Wnonnull]
   16 |     ~usage_requirements() { ((Model*)0)->~Model(); }
      |                             ~~~~~~~~~~~~~~~~~~~^~
./boost/concept/usage.hpp:30:7: note: in a call to non-static member function ‘boost::SinglePassRangeConcept<T>::~SinglePassRangeConcept() [with T = const boost::iterator_range<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >]’
   30 |       ~model()
      |       ^
./boost/range/concepts.hpp:284:9: note: in expansion of macro ‘BOOST_CONCEPT_USAGE’
  284 |         BOOST_CONCEPT_USAGE(SinglePassRangeConcept)
      |         ^~~~~~~~~~~~~~~~~~~

    "g++"   -fvisibility-inlines-hidden -m64 -pthread -O3 -finline-functions -Wno-inline -Wall -pedantic -fvisibility=hidden -Wextra -Wno-long-long -Wno-unused-parameter -Wunused-function -pedantic -DBOOST_ALL_NO_LIB=1 -DBOOST_SYSTEM_STATIC_LINK=1 -DBOOST_THREAD_BUILD_LIB=1 -DBOOST_THREAD_DONT_USE_CHRONO -DBOOST_THREAD_POSIX -DNDEBUG  -I"." -c -o "bin.v2/libs/thread/build/gcc-13.3.0/release/link-static/threadapi-pthread/threading-multi/visibility-hidden/pthread/thread.o" "libs/thread/src/pthread/thread.cpp"

...failed gcc.compile.c++ bin.v2/libs/thread/build/gcc-13.3.0/release/link-static/threadapi-pthread/threading-multi/visibility-hidden/pthread/thread.o...
...skipped <pbin.v2/libs/thread/build/gcc-13.3.0/release/link-static/threadapi-pthread/threading-multi/visibility-hidden>libboost_thread.a(clean) for lack of <pbin.v2/libs/thread/build/gcc-13.3.0/release/link-static/threadapi-pthread/threading-multi/visibility-hidden>pthread/thread.o...
...skipped <pbin.v2/libs/thread/build/gcc-13.3.0/release/link-static/threadapi-pthread/threading-multi/visibility-hidden>libboost_thread.a for lack of <pbin.v2/libs/thread/build/gcc-13.3.0/release/link-static/threadapi-pthread/threading-multi/visibility-hidden>pthread/thread.o...
...skipped <p/usr/local/lib>libboost_thread.a for lack of <pbin.v2/libs/thread/build/gcc-13.3.0/release/link-static/threadapi-pthread/threading-multi/visibility-hidden>libboost_thread.a...
gcc.compile.c++ bin.v2/libs/coroutine/build/gcc-13.3.0/release/link-static/threadapi-pthread/threading-multi/visibility-hidden/posix/stack_traits.o
In file included from ./boost/coroutine/stack_traits.hpp:14,
                 from libs/coroutine/src/posix/stack_traits.cpp:7:
./boost/coroutine/detail/config.hpp:17:4: warning: #warning "Boost.Coroutine is now deprecated. Please switch to Boost.Coroutine2. To disable this warning message, define BOOST_COROUTINES_NO_DEPRECATION_WARNING." [-Wcpp]
   17 | #  warning                  "Boost.Coroutine is now deprecated. Please switch to Boost.Coroutine2. To disable this warning message, define BOOST_COROUTINES_NO_DEPRECATION_WARNING."
      |    ^~~~~~~
In file included from /usr/include/pthread.h:33,
                 from /usr/include/x86_64-linux-gnu/c++/13/bits/gthr-default.h:35,
                 from /usr/include/x86_64-linux-gnu/c++/13/bits/gthr.h:148,
                 from /usr/include/c++/13/ext/atomicity.h:35,
                 from /usr/include/c++/13/bits/ios_base.h:39,
                 from /usr/include/c++/13/ios:44,
                 from /usr/include/c++/13/ostream:40,
                 from ./boost/system/error_code.hpp:17,
                 from ./boost/system/system_error.hpp:11,
                 from ./boost/thread/exceptions.hpp:22,
                 from ./boost/thread/pthread/thread_data.hpp:10,
                 from ./boost/thread/thread_only.hpp:17,
                 from ./boost/thread/thread.hpp:12,
                 from ./boost/thread.hpp:13,
                 from libs/coroutine/src/posix/stack_traits.cpp:22:
./boost/thread/pthread/thread_data.hpp:60:5: error: missing binary operator before token "("
   60 | #if PTHREAD_STACK_MIN > 0
      |     ^~~~~~~~~~~~~~~~~
In file included from ./boost/functional/hash.hpp:6,
                 from ./boost/thread/detail/thread.hpp:38,
                 from ./boost/thread/thread_only.hpp:22:
./boost/container_hash/hash.hpp:130:33: warning: ‘template<class _Arg, class _Result> struct std::unary_function’ is deprecated [-Wdeprecated-declarations]
  130 |         struct hash_base : std::unary_function<T, std::size_t> {};
      |                                 ^~~~~~~~~~~~~~
In file included from /usr/include/c++/13/string:49,
                 from ./boost/thread/exceptions.hpp:20:
/usr/include/c++/13/bits/stl_function.h:117:12: note: declared here
  117 |     struct unary_function
      |            ^~~~~~~~~~~~~~

    "g++"   -fvisibility-inlines-hidden -m64 -pthread -O3 -finline-functions -Wno-inline -Wall -fvisibility=hidden  -DBOOST_ALL_NO_LIB=1 -DBOOST_CHRONO_STATIC_LINK=1 -DBOOST_COROUTINES_SOURCE -DBOOST_DISABLE_ASSERTS -DBOOST_SYSTEM_STATIC_LINK=1 -DBOOST_THREAD_BUILD_LIB=1 -DBOOST_THREAD_POSIX -DBOOST_THREAD_USE_LIB=1 -DNDEBUG  -I"." -c -o "bin.v2/libs/coroutine/build/gcc-13.3.0/release/link-static/threadapi-pthread/threading-multi/visibility-hidden/posix/stack_traits.o" "libs/coroutine/src/posix/stack_traits.cpp"

...failed gcc.compile.c++ bin.v2/libs/coroutine/build/gcc-13.3.0/release/link-static/threadapi-pthread/threading-multi/visibility-hidden/posix/stack_traits.o...
...skipped <pbin.v2/libs/coroutine/build/gcc-13.3.0/release/link-static/threadapi-pthread/threading-multi/visibility-hidden>libboost_coroutine.a(clean) for lack of <pbin.v2/libs/coroutine/build/gcc-13.3.0/release/link-static/threadapi-pthread/threading-multi/visibility-hidden>posix/stack_traits.o...
...skipped <pbin.v2/libs/coroutine/build/gcc-13.3.0/release/link-static/threadapi-pthread/threading-multi/visibility-hidden>libboost_coroutine.a for lack of <pbin.v2/libs/coroutine/build/gcc-13.3.0/release/link-static/threadapi-pthread/threading-multi/visibility-hidden>posix/stack_traits.o...
...skipped <p/usr/local/lib>libboost_coroutine.a for lack of <pbin.v2/libs/coroutine/build/gcc-13.3.0/release/link-static/threadapi-pthread/threading-multi/visibility-hidden>libboost_coroutine.a...
gcc.compile.c++ bin.v2/libs/log/build/gcc-13.3.0/release/link-static/threadapi-pthread/threading-multi/visibility-hidden/severity_level.o
In file included from /usr/include/x86_64-linux-gnu/bits/local_lim.h:81,
                 from /usr/include/x86_64-linux-gnu/bits/posix1_lim.h:161,
                 from /usr/include/limits.h:195,
                 from /usr/lib/gcc/x86_64-linux-gnu/13/include/limits.h:205,
                 from /usr/lib/gcc/x86_64-linux-gnu/13/include/syslimits.h:7,
                 from /usr/lib/gcc/x86_64-linux-gnu/13/include/limits.h:34,
                 from ./boost/log/detail/config.hpp:33,
                 from libs/log/src/severity_level.cpp:16:
./boost/thread/pthread/thread_data.hpp:60:5: error: missing binary operator before token "("
   60 | #if PTHREAD_STACK_MIN > 0
      |     ^~~~~~~~~~~~~~~~~
In file included from ./boost/functional/hash.hpp:6,
                 from ./boost/thread/detail/thread.hpp:38,
                 from ./boost/thread/thread_only.hpp:22,
                 from ./boost/thread/thread.hpp:12,
                 from libs/log/src/severity_level.cpp:23:
./boost/container_hash/hash.hpp:130:33: warning: ‘template<class _Arg, class _Result> struct std::unary_function’ is deprecated [-Wdeprecated-declarations]
  130 |         struct hash_base : std::unary_function<T, std::size_t> {};
      |                                 ^~~~~~~~~~~~~~
In file included from /usr/include/c++/13/functional:49,
                 from ./boost/config/no_tr1/functional.hpp:21,
                 from ./boost/smart_ptr/intrusive_ptr.hpp:24,
                 from ./boost/log/sources/severity_feature.hpp:20,
                 from libs/log/src/severity_level.cpp:18:
/usr/include/c++/13/bits/stl_function.h:117:12: note: declared here
  117 |     struct unary_function
      |            ^~~~~~~~~~~~~~

    "g++"   -fvisibility-inlines-hidden -m64 -pthread -O3 -finline-functions -Wno-inline -Wall -fvisibility=hidden -fno-strict-aliasing -ftemplate-depth-1024 -DBOOST_ALL_NO_LIB=1 -DBOOST_ATOMIC_STATIC_LINK=1 -DBOOST_CHRONO_STATIC_LINK=1 -DBOOST_FILESYSTEM_STATIC_LINK=1 -DBOOST_LOG_BUILDING_THE_LIB=1 -DBOOST_LOG_HAS_PTHREAD_MUTEX_ROBUST -DBOOST_LOG_USE_AVX2 -DBOOST_LOG_USE_NATIVE_SYSLOG -DBOOST_LOG_USE_SSSE3 -DBOOST_LOG_WITHOUT_DEBUG_OUTPUT -DBOOST_LOG_WITHOUT_EVENT_LOG -DBOOST_SPIRIT_USE_PHOENIX_V3=1 -DBOOST_SYSTEM_STATIC_LINK=1 -DBOOST_THREAD_BUILD_LIB=1 -DBOOST_THREAD_DONT_USE_CHRONO=1 -DBOOST_THREAD_POSIX -DBOOST_THREAD_USE_LIB=1 -DDATE_TIME_INLINE -DNDEBUG -D_XOPEN_SOURCE=600 -D__STDC_CONSTANT_MACROS  -I"." -I"libs/log/src" -c -o "bin.v2/libs/log/build/gcc-13.3.0/release/link-static/threadapi-pthread/threading-multi/visibility-hidden/severity_level.o" "libs/log/src/severity_level.cpp"

...failed gcc.compile.c++ bin.v2/libs/log/build/gcc-13.3.0/release/link-static/threadapi-pthread/threading-multi/visibility-hidden/severity_level.o...
gcc.compile.c++ bin.v2/libs/log/build/gcc-13.3.0/release/link-static/threadapi-pthread/threading-multi/visibility-hidden/event.o
In file included from /usr/include/x86_64-linux-gnu/bits/local_lim.h:81,
                 from /usr/include/x86_64-linux-gnu/bits/posix1_lim.h:161,
                 from /usr/include/limits.h:195,
                 from /usr/lib/gcc/x86_64-linux-gnu/13/include/limits.h:205,
                 from /usr/lib/gcc/x86_64-linux-gnu/13/include/syslimits.h:7,
                 from /usr/lib/gcc/x86_64-linux-gnu/13/include/limits.h:34,
                 from ./boost/log/detail/config.hpp:33,
                 from libs/log/src/event.cpp:16:
./boost/thread/pthread/thread_data.hpp:60:5: error: missing binary operator before token "("
   60 | #if PTHREAD_STACK_MIN > 0
      |     ^~~~~~~~~~~~~~~~~

    "g++"   -fvisibility-inlines-hidden -m64 -pthread -O3 -finline-functions -Wno-inline -Wall -fvisibility=hidden -fno-strict-aliasing -ftemplate-depth-1024 -DBOOST_ALL_NO_LIB=1 -DBOOST_ATOMIC_STATIC_LINK=1 -DBOOST_CHRONO_STATIC_LINK=1 -DBOOST_FILESYSTEM_STATIC_LINK=1 -DBOOST_LOG_BUILDING_THE_LIB=1 -DBOOST_LOG_HAS_PTHREAD_MUTEX_ROBUST -DBOOST_LOG_USE_AVX2 -DBOOST_LOG_USE_NATIVE_SYSLOG -DBOOST_LOG_USE_SSSE3 -DBOOST_LOG_WITHOUT_DEBUG_OUTPUT -DBOOST_LOG_WITHOUT_EVENT_LOG -DBOOST_SPIRIT_USE_PHOENIX_V3=1 -DBOOST_SYSTEM_STATIC_LINK=1 -DBOOST_THREAD_BUILD_LIB=1 -DBOOST_THREAD_DONT_USE_CHRONO=1 -DBOOST_THREAD_POSIX -DBOOST_THREAD_USE_LIB=1 -DDATE_TIME_INLINE -DNDEBUG -D_XOPEN_SOURCE=600 -D__STDC_CONSTANT_MACROS  -I"." -I"libs/log/src" -c -o "bin.v2/libs/log/build/gcc-13.3.0/release/link-static/threadapi-pthread/threading-multi/visibility-hidden/event.o" "libs/log/src/event.cpp"

...failed gcc.compile.c++ bin.v2/libs/log/build/gcc-13.3.0/release/link-static/threadapi-pthread/threading-multi/visibility-hidden/event.o...
...skipped <pbin.v2/libs/log/build/gcc-13.3.0/release/link-static/threadapi-pthread/threading-multi/visibility-hidden>libboost_log.a(clean) for lack of <pbin.v2/libs/log/build/gcc-13.3.0/release/link-static/threadapi-pthread/threading-multi/visibility-hidden>severity_level.o...
...skipped <pbin.v2/libs/log/build/gcc-13.3.0/release/link-static/threadapi-pthread/threading-multi/visibility-hidden>libboost_log.a for lack of <pbin.v2/libs/log/build/gcc-13.3.0/release/link-static/threadapi-pthread/threading-multi/visibility-hidden>severity_level.o...
...skipped <p/usr/local/lib>libboost_log.a for lack of <pbin.v2/libs/log/build/gcc-13.3.0/release/link-static/threadapi-pthread/threading-multi/visibility-hidden>libboost_log.a...
gcc.compile.c++ bin.v2/libs/log/build/gcc-13.3.0/release/link-static/threadapi-pthread/threading-multi/visibility-hidden/setup/init_from_settings.o
In file included from /usr/include/x86_64-linux-gnu/bits/local_lim.h:81,
                 from /usr/include/x86_64-linux-gnu/bits/posix1_lim.h:161,
                 from /usr/include/limits.h:195,
                 from /usr/lib/gcc/x86_64-linux-gnu/13/include/limits.h:205,
                 from /usr/lib/gcc/x86_64-linux-gnu/13/include/syslimits.h:7,
                 from /usr/lib/gcc/x86_64-linux-gnu/13/include/limits.h:34,
                 from ./boost/log/detail/config.hpp:33,
                 from ./boost/log/detail/setup_config.hpp:20,
                 from libs/log/src/setup/init_from_settings.cpp:26:
./boost/thread/pthread/thread_data.hpp:60:5: error: missing binary operator before token "("
   60 | #if PTHREAD_STACK_MIN > 0
      |     ^~~~~~~~~~~~~~~~~
In file included from ./boost/functional/hash.hpp:6,
                 from ./boost/thread/detail/thread.hpp:38,
                 from ./boost/thread/thread_only.hpp:22,
                 from ./boost/thread/thread.hpp:12,
                 from ./boost/log/sinks/async_frontend.hpp:39,
                 from ./boost/log/sinks.hpp:25,
                 from libs/log/src/setup/init_from_settings.cpp:54:
./boost/container_hash/hash.hpp:130:33: warning: ‘template<class _Arg, class _Result> struct std::unary_function’ is deprecated [-Wdeprecated-declarations]
  130 |         struct hash_base : std::unary_function<T, std::size_t> {};
      |                                 ^~~~~~~~~~~~~~
In file included from /usr/include/c++/13/string:49,
                 from /usr/include/c++/13/bits/locale_classes.h:40,
                 from /usr/include/c++/13/bits/ios_base.h:41,
                 from /usr/include/c++/13/ios:44,
                 from libs/log/src/setup/init_from_settings.cpp:28:
/usr/include/c++/13/bits/stl_function.h:117:12: note: declared here
  117 |     struct unary_function
      |            ^~~~~~~~~~~~~~

    "g++"   -fvisibility-inlines-hidden -m64 -pthread -O3 -finline-functions -Wno-inline -Wall -fvisibility=hidden -fno-strict-aliasing -ftemplate-depth-1024 -DBOOST_ALL_NO_LIB=1 -DBOOST_ATOMIC_STATIC_LINK=1 -DBOOST_CHRONO_STATIC_LINK=1 -DBOOST_FILESYSTEM_STATIC_LINK=1 -DBOOST_LOG_HAS_PTHREAD_MUTEX_ROBUST -DBOOST_LOG_SETUP_BUILDING_THE_LIB=1 -DBOOST_LOG_USE_AVX2 -DBOOST_LOG_USE_NATIVE_SYSLOG -DBOOST_LOG_USE_SSSE3 -DBOOST_LOG_WITHOUT_EVENT_LOG -DBOOST_SPIRIT_USE_PHOENIX_V3=1 -DBOOST_SYSTEM_STATIC_LINK=1 -DBOOST_THREAD_BUILD_LIB=1 -DBOOST_THREAD_DONT_USE_CHRONO=1 -DBOOST_THREAD_POSIX -DBOOST_THREAD_USE_LIB=1 -DDATE_TIME_INLINE -DNDEBUG -D_XOPEN_SOURCE=600 -D__STDC_CONSTANT_MACROS  -I"." -I"libs/log/src" -c -o "bin.v2/libs/log/build/gcc-13.3.0/release/link-static/threadapi-pthread/threading-multi/visibility-hidden/setup/init_from_settings.o" "libs/log/src/setup/init_from_settings.cpp"

...failed gcc.compile.c++ bin.v2/libs/log/build/gcc-13.3.0/release/link-static/threadapi-pthread/threading-multi/visibility-hidden/setup/init_from_settings.o...
...skipped <pbin.v2/libs/log/build/gcc-13.3.0/release/link-static/threadapi-pthread/threading-multi/visibility-hidden>libboost_log_setup.a(clean) for lack of <pbin.v2/libs/log/build/gcc-13.3.0/release/link-static/threadapi-pthread/threading-multi/visibility-hidden>setup/init_from_settings.o...
...skipped <pbin.v2/libs/log/build/gcc-13.3.0/release/link-static/threadapi-pthread/threading-multi/visibility-hidden>libboost_log_setup.a for lack of <pbin.v2/libs/log/build/gcc-13.3.0/release/link-static/threadapi-pthread/threading-multi/visibility-hidden>setup/init_from_settings.o...
...skipped <p/usr/local/lib>libboost_log_setup.a for lack of <pbin.v2/libs/log/build/gcc-13.3.0/release/link-static/threadapi-pthread/threading-multi/visibility-hidden>libboost_log_setup.a...
gcc.compile.c++ bin.v2/libs/type_erasure/build/gcc-13.3.0/release/link-static/threadapi-pthread/threading-multi/visibility-hidden/dynamic_binding.o
In file included from /usr/include/pthread.h:33,
                 from /usr/include/x86_64-linux-gnu/c++/13/bits/gthr-default.h:35,
                 from /usr/include/x86_64-linux-gnu/c++/13/bits/gthr.h:148,
                 from /usr/include/c++/13/ext/atomicity.h:35,
                 from /usr/include/c++/13/bits/shared_ptr_base.h:61,
                 from /usr/include/c++/13/bits/shared_ptr.h:53,
                 from /usr/include/c++/13/memory:80,
                 from ./boost/config/no_tr1/memory.hpp:21,
                 from ./boost/get_pointer.hpp:14,
                 from ./boost/bind/mem_fn.hpp:25,
                 from ./boost/mem_fn.hpp:22,
                 from ./boost/bind/bind.hpp:26,
                 from ./boost/bind.hpp:22,
                 from ./boost/thread/pthread/shared_mutex.hpp:12,
                 from ./boost/thread/shared_mutex.hpp:28,
                 from libs/type_erasure/src/dynamic_binding.cpp:14:
./boost/thread/pthread/thread_data.hpp:60:5: error: missing binary operator before token "("
   60 | #if PTHREAD_STACK_MIN > 0
      |     ^~~~~~~~~~~~~~~~~

    "g++"   -fvisibility-inlines-hidden -m64 -pthread -O3 -finline-functions -Wno-inline -Wall -fvisibility=hidden  -DBOOST_ALL_NO_LIB=1 -DBOOST_CHRONO_STATIC_LINK=1 -DBOOST_SYSTEM_STATIC_LINK=1 -DBOOST_THREAD_BUILD_LIB=1 -DBOOST_THREAD_POSIX -DBOOST_THREAD_USE_LIB=1 -DNDEBUG  -I"." -c -o "bin.v2/libs/type_erasure/build/gcc-13.3.0/release/link-static/threadapi-pthread/threading-multi/visibility-hidden/dynamic_binding.o" "libs/type_erasure/src/dynamic_binding.cpp"

...failed gcc.compile.c++ bin.v2/libs/type_erasure/build/gcc-13.3.0/release/link-static/threadapi-pthread/threading-multi/visibility-hidden/dynamic_binding.o...
...skipped <pbin.v2/libs/type_erasure/build/gcc-13.3.0/release/link-static/threadapi-pthread/threading-multi/visibility-hidden>libboost_type_erasure.a(clean) for lack of <pbin.v2/libs/type_erasure/build/gcc-13.3.0/release/link-static/threadapi-pthread/threading-multi/visibility-hidden>dynamic_binding.o...
...skipped <pbin.v2/libs/type_erasure/build/gcc-13.3.0/release/link-static/threadapi-pthread/threading-multi/visibility-hidden>libboost_type_erasure.a for lack of <pbin.v2/libs/type_erasure/build/gcc-13.3.0/release/link-static/threadapi-pthread/threading-multi/visibility-hidden>dynamic_binding.o...
...skipped <p/usr/local/lib>libboost_type_erasure.a for lack of <pbin.v2/libs/type_erasure/build/gcc-13.3.0/release/link-static/threadapi-pthread/threading-multi/visibility-hidden>libboost_type_erasure.a...
gcc.compile.c++ bin.v2/libs/thread/build/gcc-13.3.0/release/threadapi-pthread/threading-multi/visibility-hidden/pthread/thread.o
In file included from /usr/include/pthread.h:33,
                 from /usr/include/x86_64-linux-gnu/c++/13/bits/gthr-default.h:35,
                 from /usr/include/x86_64-linux-gnu/c++/13/bits/gthr.h:148,
                 from /usr/include/c++/13/ext/atomicity.h:35,
                 from /usr/include/c++/13/bits/ios_base.h:39,
                 from /usr/include/c++/13/ios:44,
                 from /usr/include/c++/13/ostream:40,
                 from ./boost/system/error_code.hpp:17,
                 from ./boost/system/system_error.hpp:11,
                 from ./boost/thread/exceptions.hpp:22,
                 from ./boost/thread/pthread/thread_data.hpp:10,
                 from ./boost/thread/thread_only.hpp:17,
                 from libs/thread/src/pthread/thread.cpp:11:
./boost/thread/pthread/thread_data.hpp:60:5: error: missing binary operator before token "("
   60 | #if PTHREAD_STACK_MIN > 0
      |     ^~~~~~~~~~~~~~~~~
In file included from ./boost/functional/hash.hpp:6,
                 from ./boost/thread/detail/thread.hpp:38,
                 from ./boost/thread/thread_only.hpp:22:
./boost/container_hash/hash.hpp:130:33: warning: ‘template<class _Arg, class _Result> struct std::unary_function’ is deprecated [-Wdeprecated-declarations]
  130 |         struct hash_base : std::unary_function<T, std::size_t> {};
      |                                 ^~~~~~~~~~~~~~
In file included from /usr/include/c++/13/string:49,
                 from ./boost/thread/exceptions.hpp:20:
/usr/include/c++/13/bits/stl_function.h:117:12: note: declared here
  117 |     struct unary_function
      |            ^~~~~~~~~~~~~~
In file included from ./boost/concept/assert.hpp:35,
                 from ./boost/concept_check.hpp:20,
                 from ./boost/range/concepts.hpp:19,
                 from ./boost/range/size_type.hpp:20,
                 from ./boost/range/size.hpp:21,
                 from ./boost/range/functions.hpp:20,
                 from ./boost/range/iterator_range_core.hpp:38,
                 from ./boost/algorithm/string/iter_find.hpp:19,
                 from ./boost/algorithm/string/split.hpp:16,
                 from libs/thread/src/pthread/thread.cpp:34:
./boost/concept/detail/general.hpp: In instantiation of ‘static void boost::concepts::constraint<Model>::failed() [with Model = boost::algorithm::FinderConcept<boost::algorithm::detail::token_finderF<boost::algorithm::detail::is_any_ofF<char> >, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >]’:
./boost/algorithm/string/iter_find.hpp:77:13:   required from ‘SequenceSequenceT& boost::algorithm::iter_split(SequenceSequenceT&, RangeT&, FinderT) [with SequenceSequenceT = std::vector<std::__cxx11::basic_string<char> >; RangeT = std::__cxx11::basic_string<char>; FinderT = detail::token_finderF<detail::is_any_ofF<char> >]’
./boost/algorithm/string/split.hpp:146:50:   required from ‘SequenceSequenceT& boost::algorithm::split(SequenceSequenceT&, RangeT&, PredicateT, token_compress_mode_type) [with SequenceSequenceT = std::vector<std::__cxx11::basic_string<char> >; RangeT = std::__cxx11::basic_string<char>; PredicateT = detail::is_any_ofF<char>]’
libs/thread/src/pthread/thread.cpp:537:29:   required from here
./boost/concept/detail/general.hpp:47:52: warning: ‘this’ pointer is null [-Wnonnull]
   47 |     static void failed() { ((Model*)0)->constraints(); }
      |                            ~~~~~~~~~~~~~~~~~~~~~~~~^~
In file included from ./boost/algorithm/string/iter_find.hpp:26:
./boost/algorithm/string/concept.hpp:40:18: note: in a call to non-static member function ‘void boost::algorithm::FinderConcept<FinderT, IteratorT>::constraints() [with FinderT = boost::algorithm::detail::token_finderF<boost::algorithm::detail::is_any_ofF<char> >; IteratorT = __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> >]’
   40 |             void constraints()
      |                  ^~~~~~~~~~~
./boost/concept/detail/general.hpp: In instantiation of ‘static void boost::concepts::requirement<boost::concepts::failed************ Model::************>::failed() [with Model = boost::concepts::usage_requirements<boost::CopyConstructible<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > > >]’:
./boost/concept_check.hpp:167:5:   required from ‘struct boost::CopyConstructible<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >’
./boost/range/concepts.hpp:125:16:   required from ‘struct boost::range_detail::IncrementableIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >’
./boost/range/concepts.hpp:147:16:   required from ‘struct boost::range_detail::SinglePassIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >’
./boost/concept/detail/has_constraints.hpp:32:62:   required by substitution of ‘template<class Model> boost::concepts::detail::yes boost::concepts::detail::has_constraints_(Model*, wrap_constraints<Model, (& Model::constraints)>*) [with Model = boost::range_detail::SinglePassIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >]’
./boost/concept/detail/has_constraints.hpp:42:5:   required from ‘const bool boost::concepts::not_satisfied<boost::range_detail::SinglePassIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > > >::value’
./boost/concept/detail/has_constraints.hpp:45:51:   [ skipping 14 instantiation contexts, use -ftemplate-backtrace-limit=0 to disable ]
./boost/iterator/iterator_facade.hpp:901:3:   required from ‘typename boost::iterators::detail::enable_if_interoperable<Derived1, Derived2, typename boost::mpl::apply2<boost::iterators::detail::always_bool2, Derived1, Derived2>::type>::type boost::iterators::operator!=(const iterator_facade<Derived1, V1, TC1, Reference1, Difference1>&, const iterator_facade<Derived2, V2, TC2, Reference2, Difference2>&) [with Derived1 = transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, use_default, use_default>; V1 = std::__cxx11::basic_string<char>; TC1 = forward_traversal_tag; Reference1 = std::__cxx11::basic_string<char>; Difference1 = long int; Derived2 = transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, use_default, use_default>; V2 = std::__cxx11::basic_string<char>; TC2 = forward_traversal_tag; Reference2 = std::__cxx11::basic_string<char>; Difference2 = long int; typename detail::enable_if_interoperable<Derived1, Derived2, typename boost::mpl::apply2<detail::always_bool2, Derived1, Derived2>::type>::type = bool; typename boost::mpl::apply2<detail::always_bool2, Derived1, Derived2>::type = bool]’
/usr/include/c++/13/bits/stl_vector.h:1671:21:   required from ‘void std::vector<_Tp, _Alloc>::_M_range_initialize(_InputIterator, _InputIterator, std::input_iterator_tag) [with _InputIterator = boost::iterators::transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::iterators::use_default, boost::iterators::use_default>; _Tp = std::__cxx11::basic_string<char>; _Alloc = std::allocator<std::__cxx11::basic_string<char> >]’
/usr/include/c++/13/bits/stl_vector.h:711:23:   required from ‘std::vector<_Tp, _Alloc>::vector(_InputIterator, _InputIterator, const allocator_type&) [with _InputIterator = boost::iterators::transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::iterators::use_default, boost::iterators::use_default>; <template-parameter-2-2> = void; _Tp = std::__cxx11::basic_string<char>; _Alloc = std::allocator<std::__cxx11::basic_string<char> >; allocator_type = std::allocator<std::__cxx11::basic_string<char> >]’
./boost/algorithm/string/iter_find.hpp:178:31:   required from ‘SequenceSequenceT& boost::algorithm::iter_split(SequenceSequenceT&, RangeT&, FinderT) [with SequenceSequenceT = std::vector<std::__cxx11::basic_string<char> >; RangeT = std::__cxx11::basic_string<char>; FinderT = detail::token_finderF<detail::is_any_ofF<char> >]’
./boost/algorithm/string/split.hpp:146:50:   required from ‘SequenceSequenceT& boost::algorithm::split(SequenceSequenceT&, RangeT&, PredicateT, token_compress_mode_type) [with SequenceSequenceT = std::vector<std::__cxx11::basic_string<char> >; RangeT = std::__cxx11::basic_string<char>; PredicateT = detail::is_any_ofF<char>]’
libs/thread/src/pthread/thread.cpp:537:29:   required from here
./boost/concept/detail/general.hpp:39:47: warning: ‘this’ pointer is null [-Wnonnull]
   39 |     static void failed() { ((Model*)0)->~Model(); }
      |                            ~~~~~~~~~~~~~~~~~~~^~
In file included from ./boost/concept_check.hpp:31:
./boost/concept/usage.hpp:16:5: note: in a call to non-static member function ‘boost::concepts::usage_requirements<Model>::~usage_requirements() [with Model = boost::CopyConstructible<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >]’
   16 |     ~usage_requirements() { ((Model*)0)->~Model(); }
      |     ^
./boost/concept/detail/general.hpp: In instantiation of ‘static void boost::concepts::requirement<boost::concepts::failed************ Model::************>::failed() [with Model = boost::concepts::usage_requirements<boost::Convertible<boost::iterators::random_access_traversal_tag, boost::iterators::incrementable_traversal_tag> >]’:
./boost/concept_check.hpp:208:5:   required from ‘struct boost::Convertible<boost::iterators::random_access_traversal_tag, boost::iterators::incrementable_traversal_tag>’
./boost/concept/detail/has_constraints.hpp:32:62:   required by substitution of ‘template<class Model> boost::concepts::detail::yes boost::concepts::detail::has_constraints_(Model*, wrap_constraints<Model, (& Model::constraints)>*) [with Model = boost::Convertible<boost::iterators::random_access_traversal_tag, boost::iterators::incrementable_traversal_tag>]’
./boost/concept/detail/has_constraints.hpp:42:5:   required from ‘const bool boost::concepts::not_satisfied<boost::Convertible<boost::iterators::random_access_traversal_tag, boost::iterators::incrementable_traversal_tag> >::value’
./boost/concept/detail/has_constraints.hpp:45:51:   required from ‘struct boost::concepts::not_satisfied<boost::Convertible<boost::iterators::random_access_traversal_tag, boost::iterators::incrementable_traversal_tag> >’
./boost/concept/detail/general.hpp:51:8:   required from ‘struct boost::concepts::requirement_<void (*)(boost::Convertible<boost::iterators::random_access_traversal_tag, boost::iterators::incrementable_traversal_tag>)>’
./boost/iterator/iterator_concepts.hpp:114:7:   [ skipping 18 instantiation contexts, use -ftemplate-backtrace-limit=0 to disable ]
./boost/iterator/iterator_facade.hpp:901:3:   required from ‘typename boost::iterators::detail::enable_if_interoperable<Derived1, Derived2, typename boost::mpl::apply2<boost::iterators::detail::always_bool2, Derived1, Derived2>::type>::type boost::iterators::operator!=(const iterator_facade<Derived1, V1, TC1, Reference1, Difference1>&, const iterator_facade<Derived2, V2, TC2, Reference2, Difference2>&) [with Derived1 = transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, use_default, use_default>; V1 = std::__cxx11::basic_string<char>; TC1 = forward_traversal_tag; Reference1 = std::__cxx11::basic_string<char>; Difference1 = long int; Derived2 = transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, use_default, use_default>; V2 = std::__cxx11::basic_string<char>; TC2 = forward_traversal_tag; Reference2 = std::__cxx11::basic_string<char>; Difference2 = long int; typename detail::enable_if_interoperable<Derived1, Derived2, typename boost::mpl::apply2<detail::always_bool2, Derived1, Derived2>::type>::type = bool; typename boost::mpl::apply2<detail::always_bool2, Derived1, Derived2>::type = bool]’
/usr/include/c++/13/bits/stl_vector.h:1671:21:   required from ‘void std::vector<_Tp, _Alloc>::_M_range_initialize(_InputIterator, _InputIterator, std::input_iterator_tag) [with _InputIterator = boost::iterators::transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::iterators::use_default, boost::iterators::use_default>; _Tp = std::__cxx11::basic_string<char>; _Alloc = std::allocator<std::__cxx11::basic_string<char> >]’
/usr/include/c++/13/bits/stl_vector.h:711:23:   required from ‘std::vector<_Tp, _Alloc>::vector(_InputIterator, _InputIterator, const allocator_type&) [with _InputIterator = boost::iterators::transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::iterators::use_default, boost::iterators::use_default>; <template-parameter-2-2> = void; _Tp = std::__cxx11::basic_string<char>; _Alloc = std::allocator<std::__cxx11::basic_string<char> >; allocator_type = std::allocator<std::__cxx11::basic_string<char> >]’
./boost/algorithm/string/iter_find.hpp:178:31:   required from ‘SequenceSequenceT& boost::algorithm::iter_split(SequenceSequenceT&, RangeT&, FinderT) [with SequenceSequenceT = std::vector<std::__cxx11::basic_string<char> >; RangeT = std::__cxx11::basic_string<char>; FinderT = detail::token_finderF<detail::is_any_ofF<char> >]’
./boost/algorithm/string/split.hpp:146:50:   required from ‘SequenceSequenceT& boost::algorithm::split(SequenceSequenceT&, RangeT&, PredicateT, token_compress_mode_type) [with SequenceSequenceT = std::vector<std::__cxx11::basic_string<char> >; RangeT = std::__cxx11::basic_string<char>; PredicateT = detail::is_any_ofF<char>]’
libs/thread/src/pthread/thread.cpp:537:29:   required from here
./boost/concept/detail/general.hpp:39:47: warning: ‘this’ pointer is null [-Wnonnull]
   39 |     static void failed() { ((Model*)0)->~Model(); }
      |                            ~~~~~~~~~~~~~~~~~~~^~
./boost/concept/usage.hpp:16:5: note: in a call to non-static member function ‘boost::concepts::usage_requirements<Model>::~usage_requirements() [with Model = boost::Convertible<boost::iterators::random_access_traversal_tag, boost::iterators::incrementable_traversal_tag>]’
   16 |     ~usage_requirements() { ((Model*)0)->~Model(); }
      |     ^
./boost/concept/detail/general.hpp: In instantiation of ‘static void boost::concepts::requirement<boost::concepts::failed************ Model::************>::failed() [with Model = boost::Convertible<boost::iterators::random_access_traversal_tag, boost::iterators::incrementable_traversal_tag>]’:
./boost/iterator/iterator_concepts.hpp:114:7:   required from ‘struct boost::range_detail::IncrementableIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >’
./boost/range/concepts.hpp:147:16:   required from ‘struct boost::range_detail::SinglePassIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >’
./boost/concept/detail/has_constraints.hpp:32:62:   required by substitution of ‘template<class Model> boost::concepts::detail::yes boost::concepts::detail::has_constraints_(Model*, wrap_constraints<Model, (& Model::constraints)>*) [with Model = boost::range_detail::SinglePassIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >]’
./boost/concept/detail/has_constraints.hpp:42:5:   required from ‘const bool boost::concepts::not_satisfied<boost::range_detail::SinglePassIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > > >::value’
./boost/concept/detail/has_constraints.hpp:45:51:   required from ‘struct boost::concepts::not_satisfied<boost::range_detail::SinglePassIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > > >’
./boost/concept/detail/general.hpp:51:8:   [ skipping 13 instantiation contexts, use -ftemplate-backtrace-limit=0 to disable ]
./boost/iterator/iterator_facade.hpp:901:3:   required from ‘typename boost::iterators::detail::enable_if_interoperable<Derived1, Derived2, typename boost::mpl::apply2<boost::iterators::detail::always_bool2, Derived1, Derived2>::type>::type boost::iterators::operator!=(const iterator_facade<Derived1, V1, TC1, Reference1, Difference1>&, const iterator_facade<Derived2, V2, TC2, Reference2, Difference2>&) [with Derived1 = transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, use_default, use_default>; V1 = std::__cxx11::basic_string<char>; TC1 = forward_traversal_tag; Reference1 = std::__cxx11::basic_string<char>; Difference1 = long int; Derived2 = transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, use_default, use_default>; V2 = std::__cxx11::basic_string<char>; TC2 = forward_traversal_tag; Reference2 = std::__cxx11::basic_string<char>; Difference2 = long int; typename detail::enable_if_interoperable<Derived1, Derived2, typename boost::mpl::apply2<detail::always_bool2, Derived1, Derived2>::type>::type = bool; typename boost::mpl::apply2<detail::always_bool2, Derived1, Derived2>::type = bool]’
/usr/include/c++/13/bits/stl_vector.h:1671:21:   required from ‘void std::vector<_Tp, _Alloc>::_M_range_initialize(_InputIterator, _InputIterator, std::input_iterator_tag) [with _InputIterator = boost::iterators::transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::iterators::use_default, boost::iterators::use_default>; _Tp = std::__cxx11::basic_string<char>; _Alloc = std::allocator<std::__cxx11::basic_string<char> >]’
/usr/include/c++/13/bits/stl_vector.h:711:23:   required from ‘std::vector<_Tp, _Alloc>::vector(_InputIterator, _InputIterator, const allocator_type&) [with _InputIterator = boost::iterators::transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::iterators::use_default, boost::iterators::use_default>; <template-parameter-2-2> = void; _Tp = std::__cxx11::basic_string<char>; _Alloc = std::allocator<std::__cxx11::basic_string<char> >; allocator_type = std::allocator<std::__cxx11::basic_string<char> >]’
./boost/algorithm/string/iter_find.hpp:178:31:   required from ‘SequenceSequenceT& boost::algorithm::iter_split(SequenceSequenceT&, RangeT&, FinderT) [with SequenceSequenceT = std::vector<std::__cxx11::basic_string<char> >; RangeT = std::__cxx11::basic_string<char>; FinderT = detail::token_finderF<detail::is_any_ofF<char> >]’
./boost/algorithm/string/split.hpp:146:50:   required from ‘SequenceSequenceT& boost::algorithm::split(SequenceSequenceT&, RangeT&, PredicateT, token_compress_mode_type) [with SequenceSequenceT = std::vector<std::__cxx11::basic_string<char> >; RangeT = std::__cxx11::basic_string<char>; PredicateT = detail::is_any_ofF<char>]’
libs/thread/src/pthread/thread.cpp:537:29:   required from here
./boost/concept/detail/general.hpp:39:47: warning: ‘this’ pointer is null [-Wnonnull]
   39 |     static void failed() { ((Model*)0)->~Model(); }
      |                            ~~~~~~~~~~~~~~~~~~~^~
./boost/concept/usage.hpp:30:7: note: in a call to non-static member function ‘boost::Convertible<X, Y>::~Convertible() [with X = boost::iterators::random_access_traversal_tag; Y = boost::iterators::incrementable_traversal_tag]’
   30 |       ~model()
      |       ^
./boost/concept_check.hpp:208:5: note: in expansion of macro ‘BOOST_CONCEPT_USAGE’
  208 |     BOOST_CONCEPT_USAGE(Convertible) {
      |     ^~~~~~~~~~~~~~~~~~~
./boost/concept/detail/general.hpp: In instantiation of ‘static void boost::concepts::requirement<boost::concepts::failed************ Model::************>::failed() [with Model = boost::concepts::usage_requirements<boost::range_detail::IncrementableIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > > >]’:
./boost/range/concepts.hpp:136:13:   required from ‘struct boost::range_detail::IncrementableIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >’
./boost/range/concepts.hpp:147:16:   required from ‘struct boost::range_detail::SinglePassIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >’
./boost/concept/detail/has_constraints.hpp:32:62:   required by substitution of ‘template<class Model> boost::concepts::detail::yes boost::concepts::detail::has_constraints_(Model*, wrap_constraints<Model, (& Model::constraints)>*) [with Model = boost::range_detail::SinglePassIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >]’
./boost/concept/detail/has_constraints.hpp:42:5:   required from ‘const bool boost::concepts::not_satisfied<boost::range_detail::SinglePassIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > > >::value’
./boost/concept/detail/has_constraints.hpp:45:51:   required from ‘struct boost::concepts::not_satisfied<boost::range_detail::SinglePassIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > > >’
./boost/concept/detail/general.hpp:51:8:   [ skipping 13 instantiation contexts, use -ftemplate-backtrace-limit=0 to disable ]
./boost/iterator/iterator_facade.hpp:901:3:   required from ‘typename boost::iterators::detail::enable_if_interoperable<Derived1, Derived2, typename boost::mpl::apply2<boost::iterators::detail::always_bool2, Derived1, Derived2>::type>::type boost::iterators::operator!=(const iterator_facade<Derived1, V1, TC1, Reference1, Difference1>&, const iterator_facade<Derived2, V2, TC2, Reference2, Difference2>&) [with Derived1 = transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, use_default, use_default>; V1 = std::__cxx11::basic_string<char>; TC1 = forward_traversal_tag; Reference1 = std::__cxx11::basic_string<char>; Difference1 = long int; Derived2 = transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, use_default, use_default>; V2 = std::__cxx11::basic_string<char>; TC2 = forward_traversal_tag; Reference2 = std::__cxx11::basic_string<char>; Difference2 = long int; typename detail::enable_if_interoperable<Derived1, Derived2, typename boost::mpl::apply2<detail::always_bool2, Derived1, Derived2>::type>::type = bool; typename boost::mpl::apply2<detail::always_bool2, Derived1, Derived2>::type = bool]’
/usr/include/c++/13/bits/stl_vector.h:1671:21:   required from ‘void std::vector<_Tp, _Alloc>::_M_range_initialize(_InputIterator, _InputIterator, std::input_iterator_tag) [with _InputIterator = boost::iterators::transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::iterators::use_default, boost::iterators::use_default>; _Tp = std::__cxx11::basic_string<char>; _Alloc = std::allocator<std::__cxx11::basic_string<char> >]’
/usr/include/c++/13/bits/stl_vector.h:711:23:   required from ‘std::vector<_Tp, _Alloc>::vector(_InputIterator, _InputIterator, const allocator_type&) [with _InputIterator = boost::iterators::transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::iterators::use_default, boost::iterators::use_default>; <template-parameter-2-2> = void; _Tp = std::__cxx11::basic_string<char>; _Alloc = std::allocator<std::__cxx11::basic_string<char> >; allocator_type = std::allocator<std::__cxx11::basic_string<char> >]’
./boost/algorithm/string/iter_find.hpp:178:31:   required from ‘SequenceSequenceT& boost::algorithm::iter_split(SequenceSequenceT&, RangeT&, FinderT) [with SequenceSequenceT = std::vector<std::__cxx11::basic_string<char> >; RangeT = std::__cxx11::basic_string<char>; FinderT = detail::token_finderF<detail::is_any_ofF<char> >]’
./boost/algorithm/string/split.hpp:146:50:   required from ‘SequenceSequenceT& boost::algorithm::split(SequenceSequenceT&, RangeT&, PredicateT, token_compress_mode_type) [with SequenceSequenceT = std::vector<std::__cxx11::basic_string<char> >; RangeT = std::__cxx11::basic_string<char>; PredicateT = detail::is_any_ofF<char>]’
libs/thread/src/pthread/thread.cpp:537:29:   required from here
./boost/concept/detail/general.hpp:39:47: warning: ‘this’ pointer is null [-Wnonnull]
   39 |     static void failed() { ((Model*)0)->~Model(); }
      |                            ~~~~~~~~~~~~~~~~~~~^~
./boost/concept/usage.hpp:16:5: note: in a call to non-static member function ‘boost::concepts::usage_requirements<Model>::~usage_requirements() [with Model = boost::range_detail::IncrementableIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >]’
   16 |     ~usage_requirements() { ((Model*)0)->~Model(); }
      |     ^
./boost/concept/detail/general.hpp: In instantiation of ‘static void boost::concepts::requirement<boost::concepts::failed************ Model::************>::failed() [with Model = boost::concepts::usage_requirements<boost::EqualityComparable<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > > >]’:
./boost/concept_check.hpp:233:5:   required from ‘struct boost::EqualityComparable<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >’
./boost/range/concepts.hpp:147:16:   required from ‘struct boost::range_detail::SinglePassIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >’
./boost/concept/detail/has_constraints.hpp:32:62:   required by substitution of ‘template<class Model> boost::concepts::detail::yes boost::concepts::detail::has_constraints_(Model*, wrap_constraints<Model, (& Model::constraints)>*) [with Model = boost::range_detail::SinglePassIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >]’
./boost/concept/detail/has_constraints.hpp:42:5:   required from ‘const bool boost::concepts::not_satisfied<boost::range_detail::SinglePassIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > > >::value’
./boost/concept/detail/has_constraints.hpp:45:51:   required from ‘struct boost::concepts::not_satisfied<boost::range_detail::SinglePassIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > > >’
./boost/concept/detail/general.hpp:51:8:   [ skipping 13 instantiation contexts, use -ftemplate-backtrace-limit=0 to disable ]
./boost/iterator/iterator_facade.hpp:901:3:   required from ‘typename boost::iterators::detail::enable_if_interoperable<Derived1, Derived2, typename boost::mpl::apply2<boost::iterators::detail::always_bool2, Derived1, Derived2>::type>::type boost::iterators::operator!=(const iterator_facade<Derived1, V1, TC1, Reference1, Difference1>&, const iterator_facade<Derived2, V2, TC2, Reference2, Difference2>&) [with Derived1 = transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, use_default, use_default>; V1 = std::__cxx11::basic_string<char>; TC1 = forward_traversal_tag; Reference1 = std::__cxx11::basic_string<char>; Difference1 = long int; Derived2 = transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, use_default, use_default>; V2 = std::__cxx11::basic_string<char>; TC2 = forward_traversal_tag; Reference2 = std::__cxx11::basic_string<char>; Difference2 = long int; typename detail::enable_if_interoperable<Derived1, Derived2, typename boost::mpl::apply2<detail::always_bool2, Derived1, Derived2>::type>::type = bool; typename boost::mpl::apply2<detail::always_bool2, Derived1, Derived2>::type = bool]’
/usr/include/c++/13/bits/stl_vector.h:1671:21:   required from ‘void std::vector<_Tp, _Alloc>::_M_range_initialize(_InputIterator, _InputIterator, std::input_iterator_tag) [with _InputIterator = boost::iterators::transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::iterators::use_default, boost::iterators::use_default>; _Tp = std::__cxx11::basic_string<char>; _Alloc = std::allocator<std::__cxx11::basic_string<char> >]’
/usr/include/c++/13/bits/stl_vector.h:711:23:   required from ‘std::vector<_Tp, _Alloc>::vector(_InputIterator, _InputIterator, const allocator_type&) [with _InputIterator = boost::iterators::transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::iterators::use_default, boost::iterators::use_default>; <template-parameter-2-2> = void; _Tp = std::__cxx11::basic_string<char>; _Alloc = std::allocator<std::__cxx11::basic_string<char> >; allocator_type = std::allocator<std::__cxx11::basic_string<char> >]’
./boost/algorithm/string/iter_find.hpp:178:31:   required from ‘SequenceSequenceT& boost::algorithm::iter_split(SequenceSequenceT&, RangeT&, FinderT) [with SequenceSequenceT = std::vector<std::__cxx11::basic_string<char> >; RangeT = std::__cxx11::basic_string<char>; FinderT = detail::token_finderF<detail::is_any_ofF<char> >]’
./boost/algorithm/string/split.hpp:146:50:   required from ‘SequenceSequenceT& boost::algorithm::split(SequenceSequenceT&, RangeT&, PredicateT, token_compress_mode_type) [with SequenceSequenceT = std::vector<std::__cxx11::basic_string<char> >; RangeT = std::__cxx11::basic_string<char>; PredicateT = detail::is_any_ofF<char>]’
libs/thread/src/pthread/thread.cpp:537:29:   required from here
./boost/concept/detail/general.hpp:39:47: warning: ‘this’ pointer is null [-Wnonnull]
   39 |     static void failed() { ((Model*)0)->~Model(); }
      |                            ~~~~~~~~~~~~~~~~~~~^~
./boost/concept/usage.hpp:16:5: note: in a call to non-static member function ‘boost::concepts::usage_requirements<Model>::~usage_requirements() [with Model = boost::EqualityComparable<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >]’
   16 |     ~usage_requirements() { ((Model*)0)->~Model(); }
      |     ^
./boost/concept/detail/general.hpp: In instantiation of ‘static void boost::concepts::requirement<boost::concepts::failed************ Model::************>::failed() [with Model = boost::concepts::usage_requirements<boost::Convertible<boost::iterators::random_access_traversal_tag, boost::iterators::single_pass_traversal_tag> >]’:
./boost/concept_check.hpp:208:5:   required from ‘struct boost::Convertible<boost::iterators::random_access_traversal_tag, boost::iterators::single_pass_traversal_tag>’
./boost/concept/detail/has_constraints.hpp:32:62:   required by substitution of ‘template<class Model> boost::concepts::detail::yes boost::concepts::detail::has_constraints_(Model*, wrap_constraints<Model, (& Model::constraints)>*) [with Model = boost::Convertible<boost::iterators::random_access_traversal_tag, boost::iterators::single_pass_traversal_tag>]’
./boost/concept/detail/has_constraints.hpp:42:5:   required from ‘const bool boost::concepts::not_satisfied<boost::Convertible<boost::iterators::random_access_traversal_tag, boost::iterators::single_pass_traversal_tag> >::value’
./boost/concept/detail/has_constraints.hpp:45:51:   required from ‘struct boost::concepts::not_satisfied<boost::Convertible<boost::iterators::random_access_traversal_tag, boost::iterators::single_pass_traversal_tag> >’
./boost/concept/detail/general.hpp:51:8:   required from ‘struct boost::concepts::requirement_<void (*)(boost::Convertible<boost::iterators::random_access_traversal_tag, boost::iterators::single_pass_traversal_tag>)>’
./boost/range/concepts.hpp:152:13:   [ skipping 17 instantiation contexts, use -ftemplate-backtrace-limit=0 to disable ]
./boost/iterator/iterator_facade.hpp:901:3:   required from ‘typename boost::iterators::detail::enable_if_interoperable<Derived1, Derived2, typename boost::mpl::apply2<boost::iterators::detail::always_bool2, Derived1, Derived2>::type>::type boost::iterators::operator!=(const iterator_facade<Derived1, V1, TC1, Reference1, Difference1>&, const iterator_facade<Derived2, V2, TC2, Reference2, Difference2>&) [with Derived1 = transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, use_default, use_default>; V1 = std::__cxx11::basic_string<char>; TC1 = forward_traversal_tag; Reference1 = std::__cxx11::basic_string<char>; Difference1 = long int; Derived2 = transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, use_default, use_default>; V2 = std::__cxx11::basic_string<char>; TC2 = forward_traversal_tag; Reference2 = std::__cxx11::basic_string<char>; Difference2 = long int; typename detail::enable_if_interoperable<Derived1, Derived2, typename boost::mpl::apply2<detail::always_bool2, Derived1, Derived2>::type>::type = bool; typename boost::mpl::apply2<detail::always_bool2, Derived1, Derived2>::type = bool]’
/usr/include/c++/13/bits/stl_vector.h:1671:21:   required from ‘void std::vector<_Tp, _Alloc>::_M_range_initialize(_InputIterator, _InputIterator, std::input_iterator_tag) [with _InputIterator = boost::iterators::transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::iterators::use_default, boost::iterators::use_default>; _Tp = std::__cxx11::basic_string<char>; _Alloc = std::allocator<std::__cxx11::basic_string<char> >]’
/usr/include/c++/13/bits/stl_vector.h:711:23:   required from ‘std::vector<_Tp, _Alloc>::vector(_InputIterator, _InputIterator, const allocator_type&) [with _InputIterator = boost::iterators::transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::iterators::use_default, boost::iterators::use_default>; <template-parameter-2-2> = void; _Tp = std::__cxx11::basic_string<char>; _Alloc = std::allocator<std::__cxx11::basic_string<char> >; allocator_type = std::allocator<std::__cxx11::basic_string<char> >]’
./boost/algorithm/string/iter_find.hpp:178:31:   required from ‘SequenceSequenceT& boost::algorithm::iter_split(SequenceSequenceT&, RangeT&, FinderT) [with SequenceSequenceT = std::vector<std::__cxx11::basic_string<char> >; RangeT = std::__cxx11::basic_string<char>; FinderT = detail::token_finderF<detail::is_any_ofF<char> >]’
./boost/algorithm/string/split.hpp:146:50:   required from ‘SequenceSequenceT& boost::algorithm::split(SequenceSequenceT&, RangeT&, PredicateT, token_compress_mode_type) [with SequenceSequenceT = std::vector<std::__cxx11::basic_string<char> >; RangeT = std::__cxx11::basic_string<char>; PredicateT = detail::is_any_ofF<char>]’
libs/thread/src/pthread/thread.cpp:537:29:   required from here
./boost/concept/detail/general.hpp:39:47: warning: ‘this’ pointer is null [-Wnonnull]
   39 |     static void failed() { ((Model*)0)->~Model(); }
      |                            ~~~~~~~~~~~~~~~~~~~^~
./boost/concept/usage.hpp:16:5: note: in a call to non-static member function ‘boost::concepts::usage_requirements<Model>::~usage_requirements() [with Model = boost::Convertible<boost::iterators::random_access_traversal_tag, boost::iterators::single_pass_traversal_tag>]’
   16 |     ~usage_requirements() { ((Model*)0)->~Model(); }
      |     ^
./boost/concept/detail/general.hpp: In instantiation of ‘static void boost::concepts::requirement<boost::concepts::failed************ Model::************>::failed() [with Model = boost::Convertible<boost::iterators::random_access_traversal_tag, boost::iterators::single_pass_traversal_tag>]’:
./boost/range/concepts.hpp:152:13:   required from ‘struct boost::range_detail::SinglePassIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >’
./boost/concept/detail/has_constraints.hpp:32:62:   required by substitution of ‘template<class Model> boost::concepts::detail::yes boost::concepts::detail::has_constraints_(Model*, wrap_constraints<Model, (& Model::constraints)>*) [with Model = boost::range_detail::SinglePassIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >]’
./boost/concept/detail/has_constraints.hpp:42:5:   required from ‘const bool boost::concepts::not_satisfied<boost::range_detail::SinglePassIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > > >::value’
./boost/concept/detail/has_constraints.hpp:45:51:   required from ‘struct boost::concepts::not_satisfied<boost::range_detail::SinglePassIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > > >’
./boost/concept/detail/general.hpp:51:8:   required from ‘struct boost::concepts::requirement_<void (*)(boost::range_detail::SinglePassIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >)>’
./boost/range/concepts.hpp:278:9:   [ skipping 12 instantiation contexts, use -ftemplate-backtrace-limit=0 to disable ]
./boost/iterator/iterator_facade.hpp:901:3:   required from ‘typename boost::iterators::detail::enable_if_interoperable<Derived1, Derived2, typename boost::mpl::apply2<boost::iterators::detail::always_bool2, Derived1, Derived2>::type>::type boost::iterators::operator!=(const iterator_facade<Derived1, V1, TC1, Reference1, Difference1>&, const iterator_facade<Derived2, V2, TC2, Reference2, Difference2>&) [with Derived1 = transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, use_default, use_default>; V1 = std::__cxx11::basic_string<char>; TC1 = forward_traversal_tag; Reference1 = std::__cxx11::basic_string<char>; Difference1 = long int; Derived2 = transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, use_default, use_default>; V2 = std::__cxx11::basic_string<char>; TC2 = forward_traversal_tag; Reference2 = std::__cxx11::basic_string<char>; Difference2 = long int; typename detail::enable_if_interoperable<Derived1, Derived2, typename boost::mpl::apply2<detail::always_bool2, Derived1, Derived2>::type>::type = bool; typename boost::mpl::apply2<detail::always_bool2, Derived1, Derived2>::type = bool]’
/usr/include/c++/13/bits/stl_vector.h:1671:21:   required from ‘void std::vector<_Tp, _Alloc>::_M_range_initialize(_InputIterator, _InputIterator, std::input_iterator_tag) [with _InputIterator = boost::iterators::transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::iterators::use_default, boost::iterators::use_default>; _Tp = std::__cxx11::basic_string<char>; _Alloc = std::allocator<std::__cxx11::basic_string<char> >]’
/usr/include/c++/13/bits/stl_vector.h:711:23:   required from ‘std::vector<_Tp, _Alloc>::vector(_InputIterator, _InputIterator, const allocator_type&) [with _InputIterator = boost::iterators::transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::iterators::use_default, boost::iterators::use_default>; <template-parameter-2-2> = void; _Tp = std::__cxx11::basic_string<char>; _Alloc = std::allocator<std::__cxx11::basic_string<char> >; allocator_type = std::allocator<std::__cxx11::basic_string<char> >]’
./boost/algorithm/string/iter_find.hpp:178:31:   required from ‘SequenceSequenceT& boost::algorithm::iter_split(SequenceSequenceT&, RangeT&, FinderT) [with SequenceSequenceT = std::vector<std::__cxx11::basic_string<char> >; RangeT = std::__cxx11::basic_string<char>; FinderT = detail::token_finderF<detail::is_any_ofF<char> >]’
./boost/algorithm/string/split.hpp:146:50:   required from ‘SequenceSequenceT& boost::algorithm::split(SequenceSequenceT&, RangeT&, PredicateT, token_compress_mode_type) [with SequenceSequenceT = std::vector<std::__cxx11::basic_string<char> >; RangeT = std::__cxx11::basic_string<char>; PredicateT = detail::is_any_ofF<char>]’
libs/thread/src/pthread/thread.cpp:537:29:   required from here
./boost/concept/detail/general.hpp:39:47: warning: ‘this’ pointer is null [-Wnonnull]
   39 |     static void failed() { ((Model*)0)->~Model(); }
      |                            ~~~~~~~~~~~~~~~~~~~^~
./boost/concept/usage.hpp:30:7: note: in a call to non-static member function ‘boost::Convertible<X, Y>::~Convertible() [with X = boost::iterators::random_access_traversal_tag; Y = boost::iterators::single_pass_traversal_tag]’
   30 |       ~model()
      |       ^
./boost/concept_check.hpp:208:5: note: in expansion of macro ‘BOOST_CONCEPT_USAGE’
  208 |     BOOST_CONCEPT_USAGE(Convertible) {
      |     ^~~~~~~~~~~~~~~~~~~
./boost/concept/detail/general.hpp: In instantiation of ‘static void boost::concepts::requirement<boost::concepts::failed************ Model::************>::failed() [with Model = boost::concepts::usage_requirements<boost::range_detail::SinglePassIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > > >]’:
./boost/range/concepts.hpp:158:13:   required from ‘struct boost::range_detail::SinglePassIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >’
./boost/concept/detail/has_constraints.hpp:32:62:   required by substitution of ‘template<class Model> boost::concepts::detail::yes boost::concepts::detail::has_constraints_(Model*, wrap_constraints<Model, (& Model::constraints)>*) [with Model = boost::range_detail::SinglePassIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >]’
./boost/concept/detail/has_constraints.hpp:42:5:   required from ‘const bool boost::concepts::not_satisfied<boost::range_detail::SinglePassIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > > >::value’
./boost/concept/detail/has_constraints.hpp:45:51:   required from ‘struct boost::concepts::not_satisfied<boost::range_detail::SinglePassIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > > >’
./boost/concept/detail/general.hpp:51:8:   required from ‘struct boost::concepts::requirement_<void (*)(boost::range_detail::SinglePassIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >)>’
./boost/range/concepts.hpp:278:9:   [ skipping 12 instantiation contexts, use -ftemplate-backtrace-limit=0 to disable ]
./boost/iterator/iterator_facade.hpp:901:3:   required from ‘typename boost::iterators::detail::enable_if_interoperable<Derived1, Derived2, typename boost::mpl::apply2<boost::iterators::detail::always_bool2, Derived1, Derived2>::type>::type boost::iterators::operator!=(const iterator_facade<Derived1, V1, TC1, Reference1, Difference1>&, const iterator_facade<Derived2, V2, TC2, Reference2, Difference2>&) [with Derived1 = transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, use_default, use_default>; V1 = std::__cxx11::basic_string<char>; TC1 = forward_traversal_tag; Reference1 = std::__cxx11::basic_string<char>; Difference1 = long int; Derived2 = transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, use_default, use_default>; V2 = std::__cxx11::basic_string<char>; TC2 = forward_traversal_tag; Reference2 = std::__cxx11::basic_string<char>; Difference2 = long int; typename detail::enable_if_interoperable<Derived1, Derived2, typename boost::mpl::apply2<detail::always_bool2, Derived1, Derived2>::type>::type = bool; typename boost::mpl::apply2<detail::always_bool2, Derived1, Derived2>::type = bool]’
/usr/include/c++/13/bits/stl_vector.h:1671:21:   required from ‘void std::vector<_Tp, _Alloc>::_M_range_initialize(_InputIterator, _InputIterator, std::input_iterator_tag) [with _InputIterator = boost::iterators::transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::iterators::use_default, boost::iterators::use_default>; _Tp = std::__cxx11::basic_string<char>; _Alloc = std::allocator<std::__cxx11::basic_string<char> >]’
/usr/include/c++/13/bits/stl_vector.h:711:23:   required from ‘std::vector<_Tp, _Alloc>::vector(_InputIterator, _InputIterator, const allocator_type&) [with _InputIterator = boost::iterators::transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::iterators::use_default, boost::iterators::use_default>; <template-parameter-2-2> = void; _Tp = std::__cxx11::basic_string<char>; _Alloc = std::allocator<std::__cxx11::basic_string<char> >; allocator_type = std::allocator<std::__cxx11::basic_string<char> >]’
./boost/algorithm/string/iter_find.hpp:178:31:   required from ‘SequenceSequenceT& boost::algorithm::iter_split(SequenceSequenceT&, RangeT&, FinderT) [with SequenceSequenceT = std::vector<std::__cxx11::basic_string<char> >; RangeT = std::__cxx11::basic_string<char>; FinderT = detail::token_finderF<detail::is_any_ofF<char> >]’
./boost/algorithm/string/split.hpp:146:50:   required from ‘SequenceSequenceT& boost::algorithm::split(SequenceSequenceT&, RangeT&, PredicateT, token_compress_mode_type) [with SequenceSequenceT = std::vector<std::__cxx11::basic_string<char> >; RangeT = std::__cxx11::basic_string<char>; PredicateT = detail::is_any_ofF<char>]’
libs/thread/src/pthread/thread.cpp:537:29:   required from here
./boost/concept/detail/general.hpp:39:47: warning: ‘this’ pointer is null [-Wnonnull]
   39 |     static void failed() { ((Model*)0)->~Model(); }
      |                            ~~~~~~~~~~~~~~~~~~~^~
./boost/concept/usage.hpp:16:5: note: in a call to non-static member function ‘boost::concepts::usage_requirements<Model>::~usage_requirements() [with Model = boost::range_detail::SinglePassIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >]’
   16 |     ~usage_requirements() { ((Model*)0)->~Model(); }
      |     ^
./boost/concept/detail/general.hpp: In instantiation of ‘static void boost::concepts::requirement<boost::concepts::failed************ Model::************>::failed() [with Model = boost::range_detail::SinglePassIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >]’:
./boost/range/concepts.hpp:278:9:   required from ‘struct boost::SinglePassRangeConcept<const boost::iterator_range<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > > >’
./boost/concept/detail/has_constraints.hpp:32:62:   required by substitution of ‘template<class Model> boost::concepts::detail::yes boost::concepts::detail::has_constraints_(Model*, wrap_constraints<Model, (& Model::constraints)>*) [with Model = boost::SinglePassRangeConcept<const boost::iterator_range<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > > >]’
./boost/concept/detail/has_constraints.hpp:42:5:   required from ‘const bool boost::concepts::not_satisfied<boost::SinglePassRangeConcept<const boost::iterator_range<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > > > >::value’
./boost/concept/detail/has_constraints.hpp:45:51:   required from ‘struct boost::concepts::not_satisfied<boost::SinglePassRangeConcept<const boost::iterator_range<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > > > >’
./boost/concept/detail/general.hpp:51:8:   required from ‘struct boost::concepts::requirement_<void (*)(boost::SinglePassRangeConcept<const boost::iterator_range<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > > >)>’
./boost/range/algorithm/equal.hpp:174:13:   [ skipping 7 instantiation contexts, use -ftemplate-backtrace-limit=0 to disable ]
./boost/iterator/iterator_facade.hpp:901:3:   required from ‘typename boost::iterators::detail::enable_if_interoperable<Derived1, Derived2, typename boost::mpl::apply2<boost::iterators::detail::always_bool2, Derived1, Derived2>::type>::type boost::iterators::operator!=(const iterator_facade<Derived1, V1, TC1, Reference1, Difference1>&, const iterator_facade<Derived2, V2, TC2, Reference2, Difference2>&) [with Derived1 = transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, use_default, use_default>; V1 = std::__cxx11::basic_string<char>; TC1 = forward_traversal_tag; Reference1 = std::__cxx11::basic_string<char>; Difference1 = long int; Derived2 = transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, use_default, use_default>; V2 = std::__cxx11::basic_string<char>; TC2 = forward_traversal_tag; Reference2 = std::__cxx11::basic_string<char>; Difference2 = long int; typename detail::enable_if_interoperable<Derived1, Derived2, typename boost::mpl::apply2<detail::always_bool2, Derived1, Derived2>::type>::type = bool; typename boost::mpl::apply2<detail::always_bool2, Derived1, Derived2>::type = bool]’
/usr/include/c++/13/bits/stl_vector.h:1671:21:   required from ‘void std::vector<_Tp, _Alloc>::_M_range_initialize(_InputIterator, _InputIterator, std::input_iterator_tag) [with _InputIterator = boost::iterators::transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::iterators::use_default, boost::iterators::use_default>; _Tp = std::__cxx11::basic_string<char>; _Alloc = std::allocator<std::__cxx11::basic_string<char> >]’
/usr/include/c++/13/bits/stl_vector.h:711:23:   required from ‘std::vector<_Tp, _Alloc>::vector(_InputIterator, _InputIterator, const allocator_type&) [with _InputIterator = boost::iterators::transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::iterators::use_default, boost::iterators::use_default>; <template-parameter-2-2> = void; _Tp = std::__cxx11::basic_string<char>; _Alloc = std::allocator<std::__cxx11::basic_string<char> >; allocator_type = std::allocator<std::__cxx11::basic_string<char> >]’
./boost/algorithm/string/iter_find.hpp:178:31:   required from ‘SequenceSequenceT& boost::algorithm::iter_split(SequenceSequenceT&, RangeT&, FinderT) [with SequenceSequenceT = std::vector<std::__cxx11::basic_string<char> >; RangeT = std::__cxx11::basic_string<char>; FinderT = detail::token_finderF<detail::is_any_ofF<char> >]’
./boost/algorithm/string/split.hpp:146:50:   required from ‘SequenceSequenceT& boost::algorithm::split(SequenceSequenceT&, RangeT&, PredicateT, token_compress_mode_type) [with SequenceSequenceT = std::vector<std::__cxx11::basic_string<char> >; RangeT = std::__cxx11::basic_string<char>; PredicateT = detail::is_any_ofF<char>]’
libs/thread/src/pthread/thread.cpp:537:29:   required from here
./boost/concept/detail/general.hpp:39:47: warning: ‘this’ pointer is null [-Wnonnull]
   39 |     static void failed() { ((Model*)0)->~Model(); }
      |                            ~~~~~~~~~~~~~~~~~~~^~
./boost/concept/usage.hpp:30:7: note: in a call to non-static member function ‘boost::range_detail::SinglePassIteratorConcept<Iterator>::~SinglePassIteratorConcept() [with Iterator = __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> >]’
   30 |       ~model()
      |       ^
./boost/range/concepts.hpp:158:13: note: in expansion of macro ‘BOOST_CONCEPT_USAGE’
  158 |             BOOST_CONCEPT_USAGE(SinglePassIteratorConcept)
      |             ^~~~~~~~~~~~~~~~~~~
./boost/concept/detail/general.hpp: In instantiation of ‘static void boost::concepts::requirement<boost::concepts::failed************ Model::************>::failed() [with Model = boost::concepts::usage_requirements<boost::SinglePassRangeConcept<const boost::iterator_range<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > > > >]’:
./boost/range/concepts.hpp:284:9:   required from ‘struct boost::SinglePassRangeConcept<const boost::iterator_range<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > > >’
./boost/concept/detail/has_constraints.hpp:32:62:   required by substitution of ‘template<class Model> boost::concepts::detail::yes boost::concepts::detail::has_constraints_(Model*, wrap_constraints<Model, (& Model::constraints)>*) [with Model = boost::SinglePassRangeConcept<const boost::iterator_range<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > > >]’
./boost/concept/detail/has_constraints.hpp:42:5:   required from ‘const bool boost::concepts::not_satisfied<boost::SinglePassRangeConcept<const boost::iterator_range<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > > > >::value’
./boost/concept/detail/has_constraints.hpp:45:51:   required from ‘struct boost::concepts::not_satisfied<boost::SinglePassRangeConcept<const boost::iterator_range<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > > > >’
./boost/concept/detail/general.hpp:51:8:   required from ‘struct boost::concepts::requirement_<void (*)(boost::SinglePassRangeConcept<const boost::iterator_range<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > > >)>’
./boost/range/algorithm/equal.hpp:174:13:   [ skipping 7 instantiation contexts, use -ftemplate-backtrace-limit=0 to disable ]
./boost/iterator/iterator_facade.hpp:901:3:   required from ‘typename boost::iterators::detail::enable_if_interoperable<Derived1, Derived2, typename boost::mpl::apply2<boost::iterators::detail::always_bool2, Derived1, Derived2>::type>::type boost::iterators::operator!=(const iterator_facade<Derived1, V1, TC1, Reference1, Difference1>&, const iterator_facade<Derived2, V2, TC2, Reference2, Difference2>&) [with Derived1 = transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, use_default, use_default>; V1 = std::__cxx11::basic_string<char>; TC1 = forward_traversal_tag; Reference1 = std::__cxx11::basic_string<char>; Difference1 = long int; Derived2 = transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, use_default, use_default>; V2 = std::__cxx11::basic_string<char>; TC2 = forward_traversal_tag; Reference2 = std::__cxx11::basic_string<char>; Difference2 = long int; typename detail::enable_if_interoperable<Derived1, Derived2, typename boost::mpl::apply2<detail::always_bool2, Derived1, Derived2>::type>::type = bool; typename boost::mpl::apply2<detail::always_bool2, Derived1, Derived2>::type = bool]’
/usr/include/c++/13/bits/stl_vector.h:1671:21:   required from ‘void std::vector<_Tp, _Alloc>::_M_range_initialize(_InputIterator, _InputIterator, std::input_iterator_tag) [with _InputIterator = boost::iterators::transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::iterators::use_default, boost::iterators::use_default>; _Tp = std::__cxx11::basic_string<char>; _Alloc = std::allocator<std::__cxx11::basic_string<char> >]’
/usr/include/c++/13/bits/stl_vector.h:711:23:   required from ‘std::vector<_Tp, _Alloc>::vector(_InputIterator, _InputIterator, const allocator_type&) [with _InputIterator = boost::iterators::transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::iterators::use_default, boost::iterators::use_default>; <template-parameter-2-2> = void; _Tp = std::__cxx11::basic_string<char>; _Alloc = std::allocator<std::__cxx11::basic_string<char> >; allocator_type = std::allocator<std::__cxx11::basic_string<char> >]’
./boost/algorithm/string/iter_find.hpp:178:31:   required from ‘SequenceSequenceT& boost::algorithm::iter_split(SequenceSequenceT&, RangeT&, FinderT) [with SequenceSequenceT = std::vector<std::__cxx11::basic_string<char> >; RangeT = std::__cxx11::basic_string<char>; FinderT = detail::token_finderF<detail::is_any_ofF<char> >]’
./boost/algorithm/string/split.hpp:146:50:   required from ‘SequenceSequenceT& boost::algorithm::split(SequenceSequenceT&, RangeT&, PredicateT, token_compress_mode_type) [with SequenceSequenceT = std::vector<std::__cxx11::basic_string<char> >; RangeT = std::__cxx11::basic_string<char>; PredicateT = detail::is_any_ofF<char>]’
libs/thread/src/pthread/thread.cpp:537:29:   required from here
./boost/concept/detail/general.hpp:39:47: warning: ‘this’ pointer is null [-Wnonnull]
   39 |     static void failed() { ((Model*)0)->~Model(); }
      |                            ~~~~~~~~~~~~~~~~~~~^~
./boost/concept/usage.hpp:16:5: note: in a call to non-static member function ‘boost::concepts::usage_requirements<Model>::~usage_requirements() [with Model = boost::SinglePassRangeConcept<const boost::iterator_range<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > > >]’
   16 |     ~usage_requirements() { ((Model*)0)->~Model(); }
      |     ^
./boost/concept/detail/general.hpp: In instantiation of ‘static void boost::concepts::requirement<boost::concepts::failed************ Model::************>::failed() [with Model = boost::SinglePassRangeConcept<const boost::iterator_range<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > > >]’:
./boost/range/algorithm/equal.hpp:174:13:   required from ‘bool boost::range::equal(const SinglePassRange1&, const SinglePassRange2&) [with SinglePassRange1 = boost::iterator_range<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >; SinglePassRange2 = boost::iterator_range<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >]’
./boost/range/iterator_range_core.hpp:646:32:   required from ‘bool boost::operator==(const iterator_range<IteratorT>&, const iterator_range<Iterator2T>&) [with Iterator1T = __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> >; Iterator2T = __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> >]’
./boost/algorithm/string/find_iterator.hpp:333:32:   required from ‘bool boost::algorithm::split_iterator<IteratorT>::equal(const boost::algorithm::split_iterator<IteratorT>&) const [with IteratorT = __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> >]’
./boost/iterator/iterator_facade.hpp:568:26:   required from ‘static bool boost::iterators::iterator_core_access::equal(const Facade1&, const Facade2&, mpl_::true_) [with Facade1 = boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >; Facade2 = boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >; mpl_::true_ = mpl_::bool_<true>]’
./boost/iterator/iterator_facade.hpp:900:3:   required from ‘typename boost::iterators::detail::enable_if_interoperable<Derived1, Derived2, typename boost::mpl::apply2<boost::iterators::detail::always_bool2, Derived1, Derived2>::type>::type boost::iterators::operator==(const iterator_facade<Derived1, V1, TC1, Reference1, Difference1>&, const iterator_facade<Derived2, V2, TC2, Reference2, Difference2>&) [with Derived1 = boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >; V1 = const boost::iterator_range<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >; TC1 = forward_traversal_tag; Reference1 = const boost::iterator_range<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >&; Difference1 = long int; Derived2 = boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >; V2 = const boost::iterator_range<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >; TC2 = forward_traversal_tag; Reference2 = const boost::iterator_range<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >&; Difference2 = long int; typename detail::enable_if_interoperable<Derived1, Derived2, typename boost::mpl::apply2<detail::always_bool2, Derived1, Derived2>::type>::type = bool; typename boost::mpl::apply2<detail::always_bool2, Derived1, Derived2>::type = bool]’
./boost/iterator/iterator_adaptor.hpp:305:29:   [ skipping 2 instantiation contexts, use -ftemplate-backtrace-limit=0 to disable ]
./boost/iterator/iterator_facade.hpp:901:3:   required from ‘typename boost::iterators::detail::enable_if_interoperable<Derived1, Derived2, typename boost::mpl::apply2<boost::iterators::detail::always_bool2, Derived1, Derived2>::type>::type boost::iterators::operator!=(const iterator_facade<Derived1, V1, TC1, Reference1, Difference1>&, const iterator_facade<Derived2, V2, TC2, Reference2, Difference2>&) [with Derived1 = transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, use_default, use_default>; V1 = std::__cxx11::basic_string<char>; TC1 = forward_traversal_tag; Reference1 = std::__cxx11::basic_string<char>; Difference1 = long int; Derived2 = transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, use_default, use_default>; V2 = std::__cxx11::basic_string<char>; TC2 = forward_traversal_tag; Reference2 = std::__cxx11::basic_string<char>; Difference2 = long int; typename detail::enable_if_interoperable<Derived1, Derived2, typename boost::mpl::apply2<detail::always_bool2, Derived1, Derived2>::type>::type = bool; typename boost::mpl::apply2<detail::always_bool2, Derived1, Derived2>::type = bool]’
/usr/include/c++/13/bits/stl_vector.h:1671:21:   required from ‘void std::vector<_Tp, _Alloc>::_M_range_initialize(_InputIterator, _InputIterator, std::input_iterator_tag) [with _InputIterator = boost::iterators::transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::iterators::use_default, boost::iterators::use_default>; _Tp = std::__cxx11::basic_string<char>; _Alloc = std::allocator<std::__cxx11::basic_string<char> >]’
/usr/include/c++/13/bits/stl_vector.h:711:23:   required from ‘std::vector<_Tp, _Alloc>::vector(_InputIterator, _InputIterator, const allocator_type&) [with _InputIterator = boost::iterators::transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::iterators::use_default, boost::iterators::use_default>; <template-parameter-2-2> = void; _Tp = std::__cxx11::basic_string<char>; _Alloc = std::allocator<std::__cxx11::basic_string<char> >; allocator_type = std::allocator<std::__cxx11::basic_string<char> >]’
./boost/algorithm/string/iter_find.hpp:178:31:   required from ‘SequenceSequenceT& boost::algorithm::iter_split(SequenceSequenceT&, RangeT&, FinderT) [with SequenceSequenceT = std::vector<std::__cxx11::basic_string<char> >; RangeT = std::__cxx11::basic_string<char>; FinderT = detail::token_finderF<detail::is_any_ofF<char> >]’
./boost/algorithm/string/split.hpp:146:50:   required from ‘SequenceSequenceT& boost::algorithm::split(SequenceSequenceT&, RangeT&, PredicateT, token_compress_mode_type) [with SequenceSequenceT = std::vector<std::__cxx11::basic_string<char> >; RangeT = std::__cxx11::basic_string<char>; PredicateT = detail::is_any_ofF<char>]’
libs/thread/src/pthread/thread.cpp:537:29:   required from here
./boost/concept/detail/general.hpp:39:47: warning: ‘this’ pointer is null [-Wnonnull]
   39 |     static void failed() { ((Model*)0)->~Model(); }
      |                            ~~~~~~~~~~~~~~~~~~~^~
./boost/concept/usage.hpp:30:7: note: in a call to non-static member function ‘boost::SinglePassRangeConcept<T>::~SinglePassRangeConcept() [with T = const boost::iterator_range<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >]’
   30 |       ~model()
      |       ^
./boost/range/concepts.hpp:284:9: note: in expansion of macro ‘BOOST_CONCEPT_USAGE’
  284 |         BOOST_CONCEPT_USAGE(SinglePassRangeConcept)
      |         ^~~~~~~~~~~~~~~~~~~
./boost/concept/usage.hpp: In instantiation of ‘boost::concepts::usage_requirements<Model>::~usage_requirements() [with Model = boost::CopyConstructible<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >]’:
./boost/concept/detail/general.hpp:39:47:   required from ‘static void boost::concepts::requirement<boost::concepts::failed************ Model::************>::failed() [with Model = boost::concepts::usage_requirements<boost::CopyConstructible<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > > >]’
./boost/concept_check.hpp:167:5:   required from ‘struct boost::CopyConstructible<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >’
./boost/range/concepts.hpp:125:16:   required from ‘struct boost::range_detail::IncrementableIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >’
./boost/range/concepts.hpp:147:16:   required from ‘struct boost::range_detail::SinglePassIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >’
./boost/concept/detail/has_constraints.hpp:32:62:   required by substitution of ‘template<class Model> boost::concepts::detail::yes boost::concepts::detail::has_constraints_(Model*, wrap_constraints<Model, (& Model::constraints)>*) [with Model = boost::range_detail::SinglePassIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >]’
./boost/concept/detail/has_constraints.hpp:42:5:   [ skipping 15 instantiation contexts, use -ftemplate-backtrace-limit=0 to disable ]
./boost/iterator/iterator_facade.hpp:901:3:   required from ‘typename boost::iterators::detail::enable_if_interoperable<Derived1, Derived2, typename boost::mpl::apply2<boost::iterators::detail::always_bool2, Derived1, Derived2>::type>::type boost::iterators::operator!=(const iterator_facade<Derived1, V1, TC1, Reference1, Difference1>&, const iterator_facade<Derived2, V2, TC2, Reference2, Difference2>&) [with Derived1 = transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, use_default, use_default>; V1 = std::__cxx11::basic_string<char>; TC1 = forward_traversal_tag; Reference1 = std::__cxx11::basic_string<char>; Difference1 = long int; Derived2 = transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, use_default, use_default>; V2 = std::__cxx11::basic_string<char>; TC2 = forward_traversal_tag; Reference2 = std::__cxx11::basic_string<char>; Difference2 = long int; typename detail::enable_if_interoperable<Derived1, Derived2, typename boost::mpl::apply2<detail::always_bool2, Derived1, Derived2>::type>::type = bool; typename boost::mpl::apply2<detail::always_bool2, Derived1, Derived2>::type = bool]’
/usr/include/c++/13/bits/stl_vector.h:1671:21:   required from ‘void std::vector<_Tp, _Alloc>::_M_range_initialize(_InputIterator, _InputIterator, std::input_iterator_tag) [with _InputIterator = boost::iterators::transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::iterators::use_default, boost::iterators::use_default>; _Tp = std::__cxx11::basic_string<char>; _Alloc = std::allocator<std::__cxx11::basic_string<char> >]’
/usr/include/c++/13/bits/stl_vector.h:711:23:   required from ‘std::vector<_Tp, _Alloc>::vector(_InputIterator, _InputIterator, const allocator_type&) [with _InputIterator = boost::iterators::transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::iterators::use_default, boost::iterators::use_default>; <template-parameter-2-2> = void; _Tp = std::__cxx11::basic_string<char>; _Alloc = std::allocator<std::__cxx11::basic_string<char> >; allocator_type = std::allocator<std::__cxx11::basic_string<char> >]’
./boost/algorithm/string/iter_find.hpp:178:31:   required from ‘SequenceSequenceT& boost::algorithm::iter_split(SequenceSequenceT&, RangeT&, FinderT) [with SequenceSequenceT = std::vector<std::__cxx11::basic_string<char> >; RangeT = std::__cxx11::basic_string<char>; FinderT = detail::token_finderF<detail::is_any_ofF<char> >]’
./boost/algorithm/string/split.hpp:146:50:   required from ‘SequenceSequenceT& boost::algorithm::split(SequenceSequenceT&, RangeT&, PredicateT, token_compress_mode_type) [with SequenceSequenceT = std::vector<std::__cxx11::basic_string<char> >; RangeT = std::__cxx11::basic_string<char>; PredicateT = detail::is_any_ofF<char>]’
libs/thread/src/pthread/thread.cpp:537:29:   required from here
./boost/concept/usage.hpp:16:48: warning: ‘this’ pointer is null [-Wnonnull]
   16 |     ~usage_requirements() { ((Model*)0)->~Model(); }
      |                             ~~~~~~~~~~~~~~~~~~~^~
./boost/concept/usage.hpp:30:7: note: in a call to non-static member function ‘boost::CopyConstructible<TT>::~CopyConstructible() [with TT = __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> >]’
   30 |       ~model()
      |       ^
./boost/concept_check.hpp:167:5: note: in expansion of macro ‘BOOST_CONCEPT_USAGE’
  167 |     BOOST_CONCEPT_USAGE(CopyConstructible) {
      |     ^~~~~~~~~~~~~~~~~~~
./boost/concept/usage.hpp: In instantiation of ‘boost::concepts::usage_requirements<Model>::~usage_requirements() [with Model = boost::Convertible<boost::iterators::random_access_traversal_tag, boost::iterators::incrementable_traversal_tag>]’:
./boost/concept/detail/general.hpp:39:47:   required from ‘static void boost::concepts::requirement<boost::concepts::failed************ Model::************>::failed() [with Model = boost::concepts::usage_requirements<boost::Convertible<boost::iterators::random_access_traversal_tag, boost::iterators::incrementable_traversal_tag> >]’
./boost/concept_check.hpp:208:5:   required from ‘struct boost::Convertible<boost::iterators::random_access_traversal_tag, boost::iterators::incrementable_traversal_tag>’
./boost/concept/detail/has_constraints.hpp:32:62:   required by substitution of ‘template<class Model> boost::concepts::detail::yes boost::concepts::detail::has_constraints_(Model*, wrap_constraints<Model, (& Model::constraints)>*) [with Model = boost::Convertible<boost::iterators::random_access_traversal_tag, boost::iterators::incrementable_traversal_tag>]’
./boost/concept/detail/has_constraints.hpp:42:5:   required from ‘const bool boost::concepts::not_satisfied<boost::Convertible<boost::iterators::random_access_traversal_tag, boost::iterators::incrementable_traversal_tag> >::value’
./boost/concept/detail/has_constraints.hpp:45:51:   required from ‘struct boost::concepts::not_satisfied<boost::Convertible<boost::iterators::random_access_traversal_tag, boost::iterators::incrementable_traversal_tag> >’
./boost/concept/detail/general.hpp:51:8:   [ skipping 19 instantiation contexts, use -ftemplate-backtrace-limit=0 to disable ]
./boost/iterator/iterator_facade.hpp:901:3:   required from ‘typename boost::iterators::detail::enable_if_interoperable<Derived1, Derived2, typename boost::mpl::apply2<boost::iterators::detail::always_bool2, Derived1, Derived2>::type>::type boost::iterators::operator!=(const iterator_facade<Derived1, V1, TC1, Reference1, Difference1>&, const iterator_facade<Derived2, V2, TC2, Reference2, Difference2>&) [with Derived1 = transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, use_default, use_default>; V1 = std::__cxx11::basic_string<char>; TC1 = forward_traversal_tag; Reference1 = std::__cxx11::basic_string<char>; Difference1 = long int; Derived2 = transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, use_default, use_default>; V2 = std::__cxx11::basic_string<char>; TC2 = forward_traversal_tag; Reference2 = std::__cxx11::basic_string<char>; Difference2 = long int; typename detail::enable_if_interoperable<Derived1, Derived2, typename boost::mpl::apply2<detail::always_bool2, Derived1, Derived2>::type>::type = bool; typename boost::mpl::apply2<detail::always_bool2, Derived1, Derived2>::type = bool]’
/usr/include/c++/13/bits/stl_vector.h:1671:21:   required from ‘void std::vector<_Tp, _Alloc>::_M_range_initialize(_InputIterator, _InputIterator, std::input_iterator_tag) [with _InputIterator = boost::iterators::transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::iterators::use_default, boost::iterators::use_default>; _Tp = std::__cxx11::basic_string<char>; _Alloc = std::allocator<std::__cxx11::basic_string<char> >]’
/usr/include/c++/13/bits/stl_vector.h:711:23:   required from ‘std::vector<_Tp, _Alloc>::vector(_InputIterator, _InputIterator, const allocator_type&) [with _InputIterator = boost::iterators::transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::iterators::use_default, boost::iterators::use_default>; <template-parameter-2-2> = void; _Tp = std::__cxx11::basic_string<char>; _Alloc = std::allocator<std::__cxx11::basic_string<char> >; allocator_type = std::allocator<std::__cxx11::basic_string<char> >]’
./boost/algorithm/string/iter_find.hpp:178:31:   required from ‘SequenceSequenceT& boost::algorithm::iter_split(SequenceSequenceT&, RangeT&, FinderT) [with SequenceSequenceT = std::vector<std::__cxx11::basic_string<char> >; RangeT = std::__cxx11::basic_string<char>; FinderT = detail::token_finderF<detail::is_any_ofF<char> >]’
./boost/algorithm/string/split.hpp:146:50:   required from ‘SequenceSequenceT& boost::algorithm::split(SequenceSequenceT&, RangeT&, PredicateT, token_compress_mode_type) [with SequenceSequenceT = std::vector<std::__cxx11::basic_string<char> >; RangeT = std::__cxx11::basic_string<char>; PredicateT = detail::is_any_ofF<char>]’
libs/thread/src/pthread/thread.cpp:537:29:   required from here
./boost/concept/usage.hpp:16:48: warning: ‘this’ pointer is null [-Wnonnull]
   16 |     ~usage_requirements() { ((Model*)0)->~Model(); }
      |                             ~~~~~~~~~~~~~~~~~~~^~
./boost/concept/usage.hpp:30:7: note: in a call to non-static member function ‘boost::Convertible<X, Y>::~Convertible() [with X = boost::iterators::random_access_traversal_tag; Y = boost::iterators::incrementable_traversal_tag]’
   30 |       ~model()
      |       ^
./boost/concept_check.hpp:208:5: note: in expansion of macro ‘BOOST_CONCEPT_USAGE’
  208 |     BOOST_CONCEPT_USAGE(Convertible) {
      |     ^~~~~~~~~~~~~~~~~~~
./boost/concept/usage.hpp: In instantiation of ‘boost::concepts::usage_requirements<Model>::~usage_requirements() [with Model = boost::range_detail::IncrementableIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >]’:
./boost/concept/detail/general.hpp:39:47:   required from ‘static void boost::concepts::requirement<boost::concepts::failed************ Model::************>::failed() [with Model = boost::concepts::usage_requirements<boost::range_detail::IncrementableIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > > >]’
./boost/range/concepts.hpp:136:13:   required from ‘struct boost::range_detail::IncrementableIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >’
./boost/range/concepts.hpp:147:16:   required from ‘struct boost::range_detail::SinglePassIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >’
./boost/concept/detail/has_constraints.hpp:32:62:   required by substitution of ‘template<class Model> boost::concepts::detail::yes boost::concepts::detail::has_constraints_(Model*, wrap_constraints<Model, (& Model::constraints)>*) [with Model = boost::range_detail::SinglePassIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >]’
./boost/concept/detail/has_constraints.hpp:42:5:   required from ‘const bool boost::concepts::not_satisfied<boost::range_detail::SinglePassIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > > >::value’
./boost/concept/detail/has_constraints.hpp:45:51:   [ skipping 14 instantiation contexts, use -ftemplate-backtrace-limit=0 to disable ]
./boost/iterator/iterator_facade.hpp:901:3:   required from ‘typename boost::iterators::detail::enable_if_interoperable<Derived1, Derived2, typename boost::mpl::apply2<boost::iterators::detail::always_bool2, Derived1, Derived2>::type>::type boost::iterators::operator!=(const iterator_facade<Derived1, V1, TC1, Reference1, Difference1>&, const iterator_facade<Derived2, V2, TC2, Reference2, Difference2>&) [with Derived1 = transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, use_default, use_default>; V1 = std::__cxx11::basic_string<char>; TC1 = forward_traversal_tag; Reference1 = std::__cxx11::basic_string<char>; Difference1 = long int; Derived2 = transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, use_default, use_default>; V2 = std::__cxx11::basic_string<char>; TC2 = forward_traversal_tag; Reference2 = std::__cxx11::basic_string<char>; Difference2 = long int; typename detail::enable_if_interoperable<Derived1, Derived2, typename boost::mpl::apply2<detail::always_bool2, Derived1, Derived2>::type>::type = bool; typename boost::mpl::apply2<detail::always_bool2, Derived1, Derived2>::type = bool]’
/usr/include/c++/13/bits/stl_vector.h:1671:21:   required from ‘void std::vector<_Tp, _Alloc>::_M_range_initialize(_InputIterator, _InputIterator, std::input_iterator_tag) [with _InputIterator = boost::iterators::transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::iterators::use_default, boost::iterators::use_default>; _Tp = std::__cxx11::basic_string<char>; _Alloc = std::allocator<std::__cxx11::basic_string<char> >]’
/usr/include/c++/13/bits/stl_vector.h:711:23:   required from ‘std::vector<_Tp, _Alloc>::vector(_InputIterator, _InputIterator, const allocator_type&) [with _InputIterator = boost::iterators::transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::iterators::use_default, boost::iterators::use_default>; <template-parameter-2-2> = void; _Tp = std::__cxx11::basic_string<char>; _Alloc = std::allocator<std::__cxx11::basic_string<char> >; allocator_type = std::allocator<std::__cxx11::basic_string<char> >]’
./boost/algorithm/string/iter_find.hpp:178:31:   required from ‘SequenceSequenceT& boost::algorithm::iter_split(SequenceSequenceT&, RangeT&, FinderT) [with SequenceSequenceT = std::vector<std::__cxx11::basic_string<char> >; RangeT = std::__cxx11::basic_string<char>; FinderT = detail::token_finderF<detail::is_any_ofF<char> >]’
./boost/algorithm/string/split.hpp:146:50:   required from ‘SequenceSequenceT& boost::algorithm::split(SequenceSequenceT&, RangeT&, PredicateT, token_compress_mode_type) [with SequenceSequenceT = std::vector<std::__cxx11::basic_string<char> >; RangeT = std::__cxx11::basic_string<char>; PredicateT = detail::is_any_ofF<char>]’
libs/thread/src/pthread/thread.cpp:537:29:   required from here
./boost/concept/usage.hpp:16:48: warning: ‘this’ pointer is null [-Wnonnull]
   16 |     ~usage_requirements() { ((Model*)0)->~Model(); }
      |                             ~~~~~~~~~~~~~~~~~~~^~
./boost/concept/usage.hpp:30:7: note: in a call to non-static member function ‘boost::range_detail::IncrementableIteratorConcept<Iterator>::~IncrementableIteratorConcept() [with Iterator = __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> >]’
   30 |       ~model()
      |       ^
./boost/range/concepts.hpp:136:13: note: in expansion of macro ‘BOOST_CONCEPT_USAGE’
  136 |             BOOST_CONCEPT_USAGE(IncrementableIteratorConcept)
      |             ^~~~~~~~~~~~~~~~~~~
./boost/concept/usage.hpp: In instantiation of ‘boost::concepts::usage_requirements<Model>::~usage_requirements() [with Model = boost::EqualityComparable<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >]’:
./boost/concept/detail/general.hpp:39:47:   required from ‘static void boost::concepts::requirement<boost::concepts::failed************ Model::************>::failed() [with Model = boost::concepts::usage_requirements<boost::EqualityComparable<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > > >]’
./boost/concept_check.hpp:233:5:   required from ‘struct boost::EqualityComparable<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >’
./boost/range/concepts.hpp:147:16:   required from ‘struct boost::range_detail::SinglePassIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >’
./boost/concept/detail/has_constraints.hpp:32:62:   required by substitution of ‘template<class Model> boost::concepts::detail::yes boost::concepts::detail::has_constraints_(Model*, wrap_constraints<Model, (& Model::constraints)>*) [with Model = boost::range_detail::SinglePassIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >]’
./boost/concept/detail/has_constraints.hpp:42:5:   required from ‘const bool boost::concepts::not_satisfied<boost::range_detail::SinglePassIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > > >::value’
./boost/concept/detail/has_constraints.hpp:45:51:   [ skipping 14 instantiation contexts, use -ftemplate-backtrace-limit=0 to disable ]
./boost/iterator/iterator_facade.hpp:901:3:   required from ‘typename boost::iterators::detail::enable_if_interoperable<Derived1, Derived2, typename boost::mpl::apply2<boost::iterators::detail::always_bool2, Derived1, Derived2>::type>::type boost::iterators::operator!=(const iterator_facade<Derived1, V1, TC1, Reference1, Difference1>&, const iterator_facade<Derived2, V2, TC2, Reference2, Difference2>&) [with Derived1 = transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, use_default, use_default>; V1 = std::__cxx11::basic_string<char>; TC1 = forward_traversal_tag; Reference1 = std::__cxx11::basic_string<char>; Difference1 = long int; Derived2 = transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, use_default, use_default>; V2 = std::__cxx11::basic_string<char>; TC2 = forward_traversal_tag; Reference2 = std::__cxx11::basic_string<char>; Difference2 = long int; typename detail::enable_if_interoperable<Derived1, Derived2, typename boost::mpl::apply2<detail::always_bool2, Derived1, Derived2>::type>::type = bool; typename boost::mpl::apply2<detail::always_bool2, Derived1, Derived2>::type = bool]’
/usr/include/c++/13/bits/stl_vector.h:1671:21:   required from ‘void std::vector<_Tp, _Alloc>::_M_range_initialize(_InputIterator, _InputIterator, std::input_iterator_tag) [with _InputIterator = boost::iterators::transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::iterators::use_default, boost::iterators::use_default>; _Tp = std::__cxx11::basic_string<char>; _Alloc = std::allocator<std::__cxx11::basic_string<char> >]’
/usr/include/c++/13/bits/stl_vector.h:711:23:   required from ‘std::vector<_Tp, _Alloc>::vector(_InputIterator, _InputIterator, const allocator_type&) [with _InputIterator = boost::iterators::transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::iterators::use_default, boost::iterators::use_default>; <template-parameter-2-2> = void; _Tp = std::__cxx11::basic_string<char>; _Alloc = std::allocator<std::__cxx11::basic_string<char> >; allocator_type = std::allocator<std::__cxx11::basic_string<char> >]’
./boost/algorithm/string/iter_find.hpp:178:31:   required from ‘SequenceSequenceT& boost::algorithm::iter_split(SequenceSequenceT&, RangeT&, FinderT) [with SequenceSequenceT = std::vector<std::__cxx11::basic_string<char> >; RangeT = std::__cxx11::basic_string<char>; FinderT = detail::token_finderF<detail::is_any_ofF<char> >]’
./boost/algorithm/string/split.hpp:146:50:   required from ‘SequenceSequenceT& boost::algorithm::split(SequenceSequenceT&, RangeT&, PredicateT, token_compress_mode_type) [with SequenceSequenceT = std::vector<std::__cxx11::basic_string<char> >; RangeT = std::__cxx11::basic_string<char>; PredicateT = detail::is_any_ofF<char>]’
libs/thread/src/pthread/thread.cpp:537:29:   required from here
./boost/concept/usage.hpp:16:48: warning: ‘this’ pointer is null [-Wnonnull]
   16 |     ~usage_requirements() { ((Model*)0)->~Model(); }
      |                             ~~~~~~~~~~~~~~~~~~~^~
./boost/concept/usage.hpp:30:7: note: in a call to non-static member function ‘boost::EqualityComparable<TT>::~EqualityComparable() [with TT = __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> >]’
   30 |       ~model()
      |       ^
./boost/concept_check.hpp:233:5: note: in expansion of macro ‘BOOST_CONCEPT_USAGE’
  233 |     BOOST_CONCEPT_USAGE(EqualityComparable) {
      |     ^~~~~~~~~~~~~~~~~~~
./boost/concept/usage.hpp: In instantiation of ‘boost::concepts::usage_requirements<Model>::~usage_requirements() [with Model = boost::Convertible<boost::iterators::random_access_traversal_tag, boost::iterators::single_pass_traversal_tag>]’:
./boost/concept/detail/general.hpp:39:47:   required from ‘static void boost::concepts::requirement<boost::concepts::failed************ Model::************>::failed() [with Model = boost::concepts::usage_requirements<boost::Convertible<boost::iterators::random_access_traversal_tag, boost::iterators::single_pass_traversal_tag> >]’
./boost/concept_check.hpp:208:5:   required from ‘struct boost::Convertible<boost::iterators::random_access_traversal_tag, boost::iterators::single_pass_traversal_tag>’
./boost/concept/detail/has_constraints.hpp:32:62:   required by substitution of ‘template<class Model> boost::concepts::detail::yes boost::concepts::detail::has_constraints_(Model*, wrap_constraints<Model, (& Model::constraints)>*) [with Model = boost::Convertible<boost::iterators::random_access_traversal_tag, boost::iterators::single_pass_traversal_tag>]’
./boost/concept/detail/has_constraints.hpp:42:5:   required from ‘const bool boost::concepts::not_satisfied<boost::Convertible<boost::iterators::random_access_traversal_tag, boost::iterators::single_pass_traversal_tag> >::value’
./boost/concept/detail/has_constraints.hpp:45:51:   required from ‘struct boost::concepts::not_satisfied<boost::Convertible<boost::iterators::random_access_traversal_tag, boost::iterators::single_pass_traversal_tag> >’
./boost/concept/detail/general.hpp:51:8:   [ skipping 18 instantiation contexts, use -ftemplate-backtrace-limit=0 to disable ]
./boost/iterator/iterator_facade.hpp:901:3:   required from ‘typename boost::iterators::detail::enable_if_interoperable<Derived1, Derived2, typename boost::mpl::apply2<boost::iterators::detail::always_bool2, Derived1, Derived2>::type>::type boost::iterators::operator!=(const iterator_facade<Derived1, V1, TC1, Reference1, Difference1>&, const iterator_facade<Derived2, V2, TC2, Reference2, Difference2>&) [with Derived1 = transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, use_default, use_default>; V1 = std::__cxx11::basic_string<char>; TC1 = forward_traversal_tag; Reference1 = std::__cxx11::basic_string<char>; Difference1 = long int; Derived2 = transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, use_default, use_default>; V2 = std::__cxx11::basic_string<char>; TC2 = forward_traversal_tag; Reference2 = std::__cxx11::basic_string<char>; Difference2 = long int; typename detail::enable_if_interoperable<Derived1, Derived2, typename boost::mpl::apply2<detail::always_bool2, Derived1, Derived2>::type>::type = bool; typename boost::mpl::apply2<detail::always_bool2, Derived1, Derived2>::type = bool]’
/usr/include/c++/13/bits/stl_vector.h:1671:21:   required from ‘void std::vector<_Tp, _Alloc>::_M_range_initialize(_InputIterator, _InputIterator, std::input_iterator_tag) [with _InputIterator = boost::iterators::transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::iterators::use_default, boost::iterators::use_default>; _Tp = std::__cxx11::basic_string<char>; _Alloc = std::allocator<std::__cxx11::basic_string<char> >]’
/usr/include/c++/13/bits/stl_vector.h:711:23:   required from ‘std::vector<_Tp, _Alloc>::vector(_InputIterator, _InputIterator, const allocator_type&) [with _InputIterator = boost::iterators::transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::iterators::use_default, boost::iterators::use_default>; <template-parameter-2-2> = void; _Tp = std::__cxx11::basic_string<char>; _Alloc = std::allocator<std::__cxx11::basic_string<char> >; allocator_type = std::allocator<std::__cxx11::basic_string<char> >]’
./boost/algorithm/string/iter_find.hpp:178:31:   required from ‘SequenceSequenceT& boost::algorithm::iter_split(SequenceSequenceT&, RangeT&, FinderT) [with SequenceSequenceT = std::vector<std::__cxx11::basic_string<char> >; RangeT = std::__cxx11::basic_string<char>; FinderT = detail::token_finderF<detail::is_any_ofF<char> >]’
./boost/algorithm/string/split.hpp:146:50:   required from ‘SequenceSequenceT& boost::algorithm::split(SequenceSequenceT&, RangeT&, PredicateT, token_compress_mode_type) [with SequenceSequenceT = std::vector<std::__cxx11::basic_string<char> >; RangeT = std::__cxx11::basic_string<char>; PredicateT = detail::is_any_ofF<char>]’
libs/thread/src/pthread/thread.cpp:537:29:   required from here
./boost/concept/usage.hpp:16:48: warning: ‘this’ pointer is null [-Wnonnull]
   16 |     ~usage_requirements() { ((Model*)0)->~Model(); }
      |                             ~~~~~~~~~~~~~~~~~~~^~
./boost/concept/usage.hpp:30:7: note: in a call to non-static member function ‘boost::Convertible<X, Y>::~Convertible() [with X = boost::iterators::random_access_traversal_tag; Y = boost::iterators::single_pass_traversal_tag]’
   30 |       ~model()
      |       ^
./boost/concept_check.hpp:208:5: note: in expansion of macro ‘BOOST_CONCEPT_USAGE’
  208 |     BOOST_CONCEPT_USAGE(Convertible) {
      |     ^~~~~~~~~~~~~~~~~~~
./boost/concept/usage.hpp: In instantiation of ‘boost::concepts::usage_requirements<Model>::~usage_requirements() [with Model = boost::range_detail::SinglePassIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >]’:
./boost/concept/detail/general.hpp:39:47:   required from ‘static void boost::concepts::requirement<boost::concepts::failed************ Model::************>::failed() [with Model = boost::concepts::usage_requirements<boost::range_detail::SinglePassIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > > >]’
./boost/range/concepts.hpp:158:13:   required from ‘struct boost::range_detail::SinglePassIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >’
./boost/concept/detail/has_constraints.hpp:32:62:   required by substitution of ‘template<class Model> boost::concepts::detail::yes boost::concepts::detail::has_constraints_(Model*, wrap_constraints<Model, (& Model::constraints)>*) [with Model = boost::range_detail::SinglePassIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >]’
./boost/concept/detail/has_constraints.hpp:42:5:   required from ‘const bool boost::concepts::not_satisfied<boost::range_detail::SinglePassIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > > >::value’
./boost/concept/detail/has_constraints.hpp:45:51:   required from ‘struct boost::concepts::not_satisfied<boost::range_detail::SinglePassIteratorConcept<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > > >’
./boost/concept/detail/general.hpp:51:8:   [ skipping 13 instantiation contexts, use -ftemplate-backtrace-limit=0 to disable ]
./boost/iterator/iterator_facade.hpp:901:3:   required from ‘typename boost::iterators::detail::enable_if_interoperable<Derived1, Derived2, typename boost::mpl::apply2<boost::iterators::detail::always_bool2, Derived1, Derived2>::type>::type boost::iterators::operator!=(const iterator_facade<Derived1, V1, TC1, Reference1, Difference1>&, const iterator_facade<Derived2, V2, TC2, Reference2, Difference2>&) [with Derived1 = transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, use_default, use_default>; V1 = std::__cxx11::basic_string<char>; TC1 = forward_traversal_tag; Reference1 = std::__cxx11::basic_string<char>; Difference1 = long int; Derived2 = transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, use_default, use_default>; V2 = std::__cxx11::basic_string<char>; TC2 = forward_traversal_tag; Reference2 = std::__cxx11::basic_string<char>; Difference2 = long int; typename detail::enable_if_interoperable<Derived1, Derived2, typename boost::mpl::apply2<detail::always_bool2, Derived1, Derived2>::type>::type = bool; typename boost::mpl::apply2<detail::always_bool2, Derived1, Derived2>::type = bool]’
/usr/include/c++/13/bits/stl_vector.h:1671:21:   required from ‘void std::vector<_Tp, _Alloc>::_M_range_initialize(_InputIterator, _InputIterator, std::input_iterator_tag) [with _InputIterator = boost::iterators::transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::iterators::use_default, boost::iterators::use_default>; _Tp = std::__cxx11::basic_string<char>; _Alloc = std::allocator<std::__cxx11::basic_string<char> >]’
/usr/include/c++/13/bits/stl_vector.h:711:23:   required from ‘std::vector<_Tp, _Alloc>::vector(_InputIterator, _InputIterator, const allocator_type&) [with _InputIterator = boost::iterators::transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::iterators::use_default, boost::iterators::use_default>; <template-parameter-2-2> = void; _Tp = std::__cxx11::basic_string<char>; _Alloc = std::allocator<std::__cxx11::basic_string<char> >; allocator_type = std::allocator<std::__cxx11::basic_string<char> >]’
./boost/algorithm/string/iter_find.hpp:178:31:   required from ‘SequenceSequenceT& boost::algorithm::iter_split(SequenceSequenceT&, RangeT&, FinderT) [with SequenceSequenceT = std::vector<std::__cxx11::basic_string<char> >; RangeT = std::__cxx11::basic_string<char>; FinderT = detail::token_finderF<detail::is_any_ofF<char> >]’
./boost/algorithm/string/split.hpp:146:50:   required from ‘SequenceSequenceT& boost::algorithm::split(SequenceSequenceT&, RangeT&, PredicateT, token_compress_mode_type) [with SequenceSequenceT = std::vector<std::__cxx11::basic_string<char> >; RangeT = std::__cxx11::basic_string<char>; PredicateT = detail::is_any_ofF<char>]’
libs/thread/src/pthread/thread.cpp:537:29:   required from here
./boost/concept/usage.hpp:16:48: warning: ‘this’ pointer is null [-Wnonnull]
   16 |     ~usage_requirements() { ((Model*)0)->~Model(); }
      |                             ~~~~~~~~~~~~~~~~~~~^~
./boost/concept/usage.hpp:30:7: note: in a call to non-static member function ‘boost::range_detail::SinglePassIteratorConcept<Iterator>::~SinglePassIteratorConcept() [with Iterator = __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> >]’
   30 |       ~model()
      |       ^
./boost/range/concepts.hpp:158:13: note: in expansion of macro ‘BOOST_CONCEPT_USAGE’
  158 |             BOOST_CONCEPT_USAGE(SinglePassIteratorConcept)
      |             ^~~~~~~~~~~~~~~~~~~
./boost/concept/usage.hpp: In instantiation of ‘boost::concepts::usage_requirements<Model>::~usage_requirements() [with Model = boost::SinglePassRangeConcept<const boost::iterator_range<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > > >]’:
./boost/concept/detail/general.hpp:39:47:   required from ‘static void boost::concepts::requirement<boost::concepts::failed************ Model::************>::failed() [with Model = boost::concepts::usage_requirements<boost::SinglePassRangeConcept<const boost::iterator_range<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > > > >]’
./boost/range/concepts.hpp:284:9:   required from ‘struct boost::SinglePassRangeConcept<const boost::iterator_range<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > > >’
./boost/concept/detail/has_constraints.hpp:32:62:   required by substitution of ‘template<class Model> boost::concepts::detail::yes boost::concepts::detail::has_constraints_(Model*, wrap_constraints<Model, (& Model::constraints)>*) [with Model = boost::SinglePassRangeConcept<const boost::iterator_range<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > > >]’
./boost/concept/detail/has_constraints.hpp:42:5:   required from ‘const bool boost::concepts::not_satisfied<boost::SinglePassRangeConcept<const boost::iterator_range<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > > > >::value’
./boost/concept/detail/has_constraints.hpp:45:51:   required from ‘struct boost::concepts::not_satisfied<boost::SinglePassRangeConcept<const boost::iterator_range<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > > > >’
./boost/concept/detail/general.hpp:51:8:   [ skipping 8 instantiation contexts, use -ftemplate-backtrace-limit=0 to disable ]
./boost/iterator/iterator_facade.hpp:901:3:   required from ‘typename boost::iterators::detail::enable_if_interoperable<Derived1, Derived2, typename boost::mpl::apply2<boost::iterators::detail::always_bool2, Derived1, Derived2>::type>::type boost::iterators::operator!=(const iterator_facade<Derived1, V1, TC1, Reference1, Difference1>&, const iterator_facade<Derived2, V2, TC2, Reference2, Difference2>&) [with Derived1 = transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, use_default, use_default>; V1 = std::__cxx11::basic_string<char>; TC1 = forward_traversal_tag; Reference1 = std::__cxx11::basic_string<char>; Difference1 = long int; Derived2 = transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, use_default, use_default>; V2 = std::__cxx11::basic_string<char>; TC2 = forward_traversal_tag; Reference2 = std::__cxx11::basic_string<char>; Difference2 = long int; typename detail::enable_if_interoperable<Derived1, Derived2, typename boost::mpl::apply2<detail::always_bool2, Derived1, Derived2>::type>::type = bool; typename boost::mpl::apply2<detail::always_bool2, Derived1, Derived2>::type = bool]’
/usr/include/c++/13/bits/stl_vector.h:1671:21:   required from ‘void std::vector<_Tp, _Alloc>::_M_range_initialize(_InputIterator, _InputIterator, std::input_iterator_tag) [with _InputIterator = boost::iterators::transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::iterators::use_default, boost::iterators::use_default>; _Tp = std::__cxx11::basic_string<char>; _Alloc = std::allocator<std::__cxx11::basic_string<char> >]’
/usr/include/c++/13/bits/stl_vector.h:711:23:   required from ‘std::vector<_Tp, _Alloc>::vector(_InputIterator, _InputIterator, const allocator_type&) [with _InputIterator = boost::iterators::transform_iterator<boost::algorithm::detail::copy_iterator_rangeF<std::__cxx11::basic_string<char>, __gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::algorithm::split_iterator<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >, boost::iterators::use_default, boost::iterators::use_default>; <template-parameter-2-2> = void; _Tp = std::__cxx11::basic_string<char>; _Alloc = std::allocator<std::__cxx11::basic_string<char> >; allocator_type = std::allocator<std::__cxx11::basic_string<char> >]’
./boost/algorithm/string/iter_find.hpp:178:31:   required from ‘SequenceSequenceT& boost::algorithm::iter_split(SequenceSequenceT&, RangeT&, FinderT) [with SequenceSequenceT = std::vector<std::__cxx11::basic_string<char> >; RangeT = std::__cxx11::basic_string<char>; FinderT = detail::token_finderF<detail::is_any_ofF<char> >]’
./boost/algorithm/string/split.hpp:146:50:   required from ‘SequenceSequenceT& boost::algorithm::split(SequenceSequenceT&, RangeT&, PredicateT, token_compress_mode_type) [with SequenceSequenceT = std::vector<std::__cxx11::basic_string<char> >; RangeT = std::__cxx11::basic_string<char>; PredicateT = detail::is_any_ofF<char>]’
libs/thread/src/pthread/thread.cpp:537:29:   required from here
./boost/concept/usage.hpp:16:48: warning: ‘this’ pointer is null [-Wnonnull]
   16 |     ~usage_requirements() { ((Model*)0)->~Model(); }
      |                             ~~~~~~~~~~~~~~~~~~~^~
./boost/concept/usage.hpp:30:7: note: in a call to non-static member function ‘boost::SinglePassRangeConcept<T>::~SinglePassRangeConcept() [with T = const boost::iterator_range<__gnu_cxx::__normal_iterator<char*, std::__cxx11::basic_string<char> > >]’
   30 |       ~model()
      |       ^
./boost/range/concepts.hpp:284:9: note: in expansion of macro ‘BOOST_CONCEPT_USAGE’
  284 |         BOOST_CONCEPT_USAGE(SinglePassRangeConcept)
      |         ^~~~~~~~~~~~~~~~~~~

    "g++"   -fvisibility-inlines-hidden -fPIC -m64 -pthread -O3 -finline-functions -Wno-inline -Wall -pedantic -fvisibility=hidden -Wextra -Wno-long-long -Wno-unused-parameter -Wunused-function -pedantic -DBOOST_ALL_NO_LIB=1 -DBOOST_SYSTEM_DYN_LINK=1 -DBOOST_THREAD_BUILD_DLL=1 -DBOOST_THREAD_DONT_USE_CHRONO -DBOOST_THREAD_POSIX -DNDEBUG  -I"." -c -o "bin.v2/libs/thread/build/gcc-13.3.0/release/threadapi-pthread/threading-multi/visibility-hidden/pthread/thread.o" "libs/thread/src/pthread/thread.cpp"

...failed gcc.compile.c++ bin.v2/libs/thread/build/gcc-13.3.0/release/threadapi-pthread/threading-multi/visibility-hidden/pthread/thread.o...
...skipped <pbin.v2/libs/thread/build/gcc-13.3.0/release/threadapi-pthread/threading-multi/visibility-hidden>libboost_thread.so.1.69.0 for lack of <pbin.v2/libs/thread/build/gcc-13.3.0/release/threadapi-pthread/threading-multi/visibility-hidden>pthread/thread.o...
...skipped <p/usr/local/lib>libboost_thread.so.1.69.0 for lack of <pbin.v2/libs/thread/build/gcc-13.3.0/release/threadapi-pthread/threading-multi/visibility-hidden>libboost_thread.so.1.69.0...
...skipped <p/usr/local/lib>libboost_thread.so for lack of <p/usr/local/lib>libboost_thread.so.1.69.0...
gcc.compile.c++ bin.v2/libs/coroutine/build/gcc-13.3.0/release/threadapi-pthread/threading-multi/visibility-hidden/posix/stack_traits.o
In file included from ./boost/coroutine/stack_traits.hpp:14,
                 from libs/coroutine/src/posix/stack_traits.cpp:7:
./boost/coroutine/detail/config.hpp:17:4: warning: #warning "Boost.Coroutine is now deprecated. Please switch to Boost.Coroutine2. To disable this warning message, define BOOST_COROUTINES_NO_DEPRECATION_WARNING." [-Wcpp]
   17 | #  warning                  "Boost.Coroutine is now deprecated. Please switch to Boost.Coroutine2. To disable this warning message, define BOOST_COROUTINES_NO_DEPRECATION_WARNING."
      |    ^~~~~~~
In file included from /usr/include/pthread.h:33,
                 from /usr/include/x86_64-linux-gnu/c++/13/bits/gthr-default.h:35,
                 from /usr/include/x86_64-linux-gnu/c++/13/bits/gthr.h:148,
                 from /usr/include/c++/13/ext/atomicity.h:35,
                 from /usr/include/c++/13/bits/ios_base.h:39,
                 from /usr/include/c++/13/ios:44,
                 from /usr/include/c++/13/ostream:40,
                 from ./boost/system/error_code.hpp:17,
                 from ./boost/system/system_error.hpp:11,
                 from ./boost/thread/exceptions.hpp:22,
                 from ./boost/thread/pthread/thread_data.hpp:10,
                 from ./boost/thread/thread_only.hpp:17,
                 from ./boost/thread/thread.hpp:12,
                 from ./boost/thread.hpp:13,
                 from libs/coroutine/src/posix/stack_traits.cpp:22:
./boost/thread/pthread/thread_data.hpp:60:5: error: missing binary operator before token "("
   60 | #if PTHREAD_STACK_MIN > 0
      |     ^~~~~~~~~~~~~~~~~
In file included from ./boost/functional/hash.hpp:6,
                 from ./boost/thread/detail/thread.hpp:38,
                 from ./boost/thread/thread_only.hpp:22:
./boost/container_hash/hash.hpp:130:33: warning: ‘template<class _Arg, class _Result> struct std::unary_function’ is deprecated [-Wdeprecated-declarations]
  130 |         struct hash_base : std::unary_function<T, std::size_t> {};
      |                                 ^~~~~~~~~~~~~~
In file included from /usr/include/c++/13/string:49,
                 from ./boost/thread/exceptions.hpp:20:
/usr/include/c++/13/bits/stl_function.h:117:12: note: declared here
  117 |     struct unary_function
      |            ^~~~~~~~~~~~~~

    "g++"   -fvisibility-inlines-hidden -fPIC -m64 -pthread -O3 -finline-functions -Wno-inline -Wall -fvisibility=hidden  -DBOOST_ALL_NO_LIB=1 -DBOOST_CHRONO_DYN_LINK=1 -DBOOST_CONTEXT_DYN_LINK=1 -DBOOST_COROUTINES_DYN_LINK=1 -DBOOST_COROUTINES_SOURCE -DBOOST_DISABLE_ASSERTS -DBOOST_SYSTEM_DYN_LINK=1 -DBOOST_THREAD_BUILD_DLL=1 -DBOOST_THREAD_POSIX -DBOOST_THREAD_USE_DLL=1 -DNDEBUG  -I"." -c -o "bin.v2/libs/coroutine/build/gcc-13.3.0/release/threadapi-pthread/threading-multi/visibility-hidden/posix/stack_traits.o" "libs/coroutine/src/posix/stack_traits.cpp"

...failed gcc.compile.c++ bin.v2/libs/coroutine/build/gcc-13.3.0/release/threadapi-pthread/threading-multi/visibility-hidden/posix/stack_traits.o...
...skipped <pbin.v2/libs/coroutine/build/gcc-13.3.0/release/threadapi-pthread/threading-multi/visibility-hidden>libboost_coroutine.so.1.69.0 for lack of <pbin.v2/libs/coroutine/build/gcc-13.3.0/release/threadapi-pthread/threading-multi/visibility-hidden>posix/stack_traits.o...
...skipped <p/usr/local/lib>libboost_coroutine.so.1.69.0 for lack of <pbin.v2/libs/coroutine/build/gcc-13.3.0/release/threadapi-pthread/threading-multi/visibility-hidden>libboost_coroutine.so.1.69.0...
...skipped <p/usr/local/lib>libboost_coroutine.so for lack of <p/usr/local/lib>libboost_coroutine.so.1.69.0...
gcc.compile.c++ bin.v2/libs/log/build/gcc-13.3.0/release/threadapi-pthread/threading-multi/visibility-hidden/severity_level.o
In file included from /usr/include/x86_64-linux-gnu/bits/local_lim.h:81,
                 from /usr/include/x86_64-linux-gnu/bits/posix1_lim.h:161,
                 from /usr/include/limits.h:195,
                 from /usr/lib/gcc/x86_64-linux-gnu/13/include/limits.h:205,
                 from /usr/lib/gcc/x86_64-linux-gnu/13/include/syslimits.h:7,
                 from /usr/lib/gcc/x86_64-linux-gnu/13/include/limits.h:34,
                 from ./boost/log/detail/config.hpp:33,
                 from libs/log/src/severity_level.cpp:16:
./boost/thread/pthread/thread_data.hpp:60:5: error: missing binary operator before token "("
   60 | #if PTHREAD_STACK_MIN > 0
      |     ^~~~~~~~~~~~~~~~~
In file included from ./boost/functional/hash.hpp:6,
                 from ./boost/thread/detail/thread.hpp:38,
                 from ./boost/thread/thread_only.hpp:22,
                 from ./boost/thread/thread.hpp:12,
                 from libs/log/src/severity_level.cpp:23:
./boost/container_hash/hash.hpp:130:33: warning: ‘template<class _Arg, class _Result> struct std::unary_function’ is deprecated [-Wdeprecated-declarations]
  130 |         struct hash_base : std::unary_function<T, std::size_t> {};
      |                                 ^~~~~~~~~~~~~~
In file included from /usr/include/c++/13/functional:49,
                 from ./boost/config/no_tr1/functional.hpp:21,
                 from ./boost/smart_ptr/intrusive_ptr.hpp:24,
                 from ./boost/log/sources/severity_feature.hpp:20,
                 from libs/log/src/severity_level.cpp:18:
/usr/include/c++/13/bits/stl_function.h:117:12: note: declared here
  117 |     struct unary_function
      |            ^~~~~~~~~~~~~~

    "g++"   -fvisibility-inlines-hidden -fPIC -m64 -pthread -O3 -finline-functions -Wno-inline -Wall -fvisibility=hidden -fno-strict-aliasing -ftemplate-depth-1024 -DBOOST_ALL_NO_LIB=1 -DBOOST_ATOMIC_DYN_LINK=1 -DBOOST_CHRONO_DYN_LINK=1 -DBOOST_DATE_TIME_DYN_LINK=1 -DBOOST_FILESYSTEM_DYN_LINK=1 -DBOOST_LOG_BUILDING_THE_LIB=1 -DBOOST_LOG_DLL -DBOOST_LOG_HAS_PTHREAD_MUTEX_ROBUST -DBOOST_LOG_USE_AVX2 -DBOOST_LOG_USE_NATIVE_SYSLOG -DBOOST_LOG_USE_SSSE3 -DBOOST_LOG_WITHOUT_DEBUG_OUTPUT -DBOOST_LOG_WITHOUT_EVENT_LOG -DBOOST_SPIRIT_USE_PHOENIX_V3=1 -DBOOST_SYSTEM_DYN_LINK=1 -DBOOST_THREAD_BUILD_DLL=1 -DBOOST_THREAD_DONT_USE_CHRONO=1 -DBOOST_THREAD_POSIX -DBOOST_THREAD_USE_DLL=1 -DDATE_TIME_INLINE -DNDEBUG -D_XOPEN_SOURCE=600 -D__STDC_CONSTANT_MACROS  -I"." -I"libs/log/src" -c -o "bin.v2/libs/log/build/gcc-13.3.0/release/threadapi-pthread/threading-multi/visibility-hidden/severity_level.o" "libs/log/src/severity_level.cpp"

...failed gcc.compile.c++ bin.v2/libs/log/build/gcc-13.3.0/release/threadapi-pthread/threading-multi/visibility-hidden/severity_level.o...
gcc.compile.c++ bin.v2/libs/log/build/gcc-13.3.0/release/threadapi-pthread/threading-multi/visibility-hidden/event.o
In file included from /usr/include/x86_64-linux-gnu/bits/local_lim.h:81,
                 from /usr/include/x86_64-linux-gnu/bits/posix1_lim.h:161,
                 from /usr/include/limits.h:195,
                 from /usr/lib/gcc/x86_64-linux-gnu/13/include/limits.h:205,
                 from /usr/lib/gcc/x86_64-linux-gnu/13/include/syslimits.h:7,
                 from /usr/lib/gcc/x86_64-linux-gnu/13/include/limits.h:34,
                 from ./boost/log/detail/config.hpp:33,
                 from libs/log/src/event.cpp:16:
./boost/thread/pthread/thread_data.hpp:60:5: error: missing binary operator before token "("
   60 | #if PTHREAD_STACK_MIN > 0
      |     ^~~~~~~~~~~~~~~~~

    "g++"   -fvisibility-inlines-hidden -fPIC -m64 -pthread -O3 -finline-functions -Wno-inline -Wall -fvisibility=hidden -fno-strict-aliasing -ftemplate-depth-1024 -DBOOST_ALL_NO_LIB=1 -DBOOST_ATOMIC_DYN_LINK=1 -DBOOST_CHRONO_DYN_LINK=1 -DBOOST_DATE_TIME_DYN_LINK=1 -DBOOST_FILESYSTEM_DYN_LINK=1 -DBOOST_LOG_BUILDING_THE_LIB=1 -DBOOST_LOG_DLL -DBOOST_LOG_HAS_PTHREAD_MUTEX_ROBUST -DBOOST_LOG_USE_AVX2 -DBOOST_LOG_USE_NATIVE_SYSLOG -DBOOST_LOG_USE_SSSE3 -DBOOST_LOG_WITHOUT_DEBUG_OUTPUT -DBOOST_LOG_WITHOUT_EVENT_LOG -DBOOST_SPIRIT_USE_PHOENIX_V3=1 -DBOOST_SYSTEM_DYN_LINK=1 -DBOOST_THREAD_BUILD_DLL=1 -DBOOST_THREAD_DONT_USE_CHRONO=1 -DBOOST_THREAD_POSIX -DBOOST_THREAD_USE_DLL=1 -DDATE_TIME_INLINE -DNDEBUG -D_XOPEN_SOURCE=600 -D__STDC_CONSTANT_MACROS  -I"." -I"libs/log/src" -c -o "bin.v2/libs/log/build/gcc-13.3.0/release/threadapi-pthread/threading-multi/visibility-hidden/event.o" "libs/log/src/event.cpp"

...failed gcc.compile.c++ bin.v2/libs/log/build/gcc-13.3.0/release/threadapi-pthread/threading-multi/visibility-hidden/event.o...
...skipped <pbin.v2/libs/log/build/gcc-13.3.0/release/threadapi-pthread/threading-multi/visibility-hidden>libboost_log.so.1.69.0 for lack of <pbin.v2/libs/log/build/gcc-13.3.0/release/threadapi-pthread/threading-multi/visibility-hidden>severity_level.o...
...skipped <p/usr/local/lib>libboost_log.so.1.69.0 for lack of <pbin.v2/libs/log/build/gcc-13.3.0/release/threadapi-pthread/threading-multi/visibility-hidden>libboost_log.so.1.69.0...
...skipped <p/usr/local/lib>libboost_log.so for lack of <p/usr/local/lib>libboost_log.so.1.69.0...
gcc.compile.c++ bin.v2/libs/log/build/gcc-13.3.0/release/threadapi-pthread/threading-multi/visibility-hidden/setup/init_from_settings.o
In file included from /usr/include/x86_64-linux-gnu/bits/local_lim.h:81,
                 from /usr/include/x86_64-linux-gnu/bits/posix1_lim.h:161,
                 from /usr/include/limits.h:195,
                 from /usr/lib/gcc/x86_64-linux-gnu/13/include/limits.h:205,
                 from /usr/lib/gcc/x86_64-linux-gnu/13/include/syslimits.h:7,
                 from /usr/lib/gcc/x86_64-linux-gnu/13/include/limits.h:34,
                 from ./boost/log/detail/config.hpp:33,
                 from ./boost/log/detail/setup_config.hpp:20,
                 from libs/log/src/setup/init_from_settings.cpp:26:
./boost/thread/pthread/thread_data.hpp:60:5: error: missing binary operator before token "("
   60 | #if PTHREAD_STACK_MIN > 0
      |     ^~~~~~~~~~~~~~~~~
In file included from ./boost/functional/hash.hpp:6,
                 from ./boost/thread/detail/thread.hpp:38,
                 from ./boost/thread/thread_only.hpp:22,
                 from ./boost/thread/thread.hpp:12,
                 from ./boost/log/sinks/async_frontend.hpp:39,
                 from ./boost/log/sinks.hpp:25,
                 from libs/log/src/setup/init_from_settings.cpp:54:
./boost/container_hash/hash.hpp:130:33: warning: ‘template<class _Arg, class _Result> struct std::unary_function’ is deprecated [-Wdeprecated-declarations]
  130 |         struct hash_base : std::unary_function<T, std::size_t> {};
      |                                 ^~~~~~~~~~~~~~
In file included from /usr/include/c++/13/string:49,
                 from /usr/include/c++/13/bits/locale_classes.h:40,
                 from /usr/include/c++/13/bits/ios_base.h:41,
                 from /usr/include/c++/13/ios:44,
                 from libs/log/src/setup/init_from_settings.cpp:28:
/usr/include/c++/13/bits/stl_function.h:117:12: note: declared here
  117 |     struct unary_function
      |            ^~~~~~~~~~~~~~

    "g++"   -fvisibility-inlines-hidden -fPIC -m64 -pthread -O3 -finline-functions -Wno-inline -Wall -fvisibility=hidden -fno-strict-aliasing -ftemplate-depth-1024 -DBOOST_ALL_NO_LIB=1 -DBOOST_ATOMIC_DYN_LINK=1 -DBOOST_CHRONO_DYN_LINK=1 -DBOOST_DATE_TIME_DYN_LINK=1 -DBOOST_FILESYSTEM_DYN_LINK=1 -DBOOST_LOG_DYN_LINK=1 -DBOOST_LOG_HAS_PTHREAD_MUTEX_ROBUST -DBOOST_LOG_SETUP_BUILDING_THE_LIB=1 -DBOOST_LOG_SETUP_DLL -DBOOST_LOG_USE_AVX2 -DBOOST_LOG_USE_NATIVE_SYSLOG -DBOOST_LOG_USE_SSSE3 -DBOOST_LOG_WITHOUT_EVENT_LOG -DBOOST_SPIRIT_USE_PHOENIX_V3=1 -DBOOST_SYSTEM_DYN_LINK=1 -DBOOST_THREAD_BUILD_DLL=1 -DBOOST_THREAD_DONT_USE_CHRONO=1 -DBOOST_THREAD_POSIX -DBOOST_THREAD_USE_DLL=1 -DDATE_TIME_INLINE -DNDEBUG -D_XOPEN_SOURCE=600 -D__STDC_CONSTANT_MACROS  -I"." -I"libs/log/src" -c -o "bin.v2/libs/log/build/gcc-13.3.0/release/threadapi-pthread/threading-multi/visibility-hidden/setup/init_from_settings.o" "libs/log/src/setup/init_from_settings.cpp"

...failed gcc.compile.c++ bin.v2/libs/log/build/gcc-13.3.0/release/threadapi-pthread/threading-multi/visibility-hidden/setup/init_from_settings.o...
...skipped <pbin.v2/libs/log/build/gcc-13.3.0/release/threadapi-pthread/threading-multi/visibility-hidden>libboost_log_setup.so.1.69.0 for lack of <pbin.v2/libs/log/build/gcc-13.3.0/release/threadapi-pthread/threading-multi/visibility-hidden>setup/init_from_settings.o...
...skipped <p/usr/local/lib>libboost_log_setup.so.1.69.0 for lack of <pbin.v2/libs/log/build/gcc-13.3.0/release/threadapi-pthread/threading-multi/visibility-hidden>libboost_log_setup.so.1.69.0...
...skipped <p/usr/local/lib>libboost_log_setup.so for lack of <p/usr/local/lib>libboost_log_setup.so.1.69.0...
gcc.compile.c++ bin.v2/libs/type_erasure/build/gcc-13.3.0/release/threadapi-pthread/threading-multi/visibility-hidden/dynamic_binding.o
In file included from /usr/include/pthread.h:33,
                 from /usr/include/x86_64-linux-gnu/c++/13/bits/gthr-default.h:35,
                 from /usr/include/x86_64-linux-gnu/c++/13/bits/gthr.h:148,
                 from /usr/include/c++/13/ext/atomicity.h:35,
                 from /usr/include/c++/13/bits/shared_ptr_base.h:61,
                 from /usr/include/c++/13/bits/shared_ptr.h:53,
                 from /usr/include/c++/13/memory:80,
                 from ./boost/config/no_tr1/memory.hpp:21,
                 from ./boost/get_pointer.hpp:14,
                 from ./boost/bind/mem_fn.hpp:25,
                 from ./boost/mem_fn.hpp:22,
                 from ./boost/bind/bind.hpp:26,
                 from ./boost/bind.hpp:22,
                 from ./boost/thread/pthread/shared_mutex.hpp:12,
                 from ./boost/thread/shared_mutex.hpp:28,
                 from libs/type_erasure/src/dynamic_binding.cpp:14:
./boost/thread/pthread/thread_data.hpp:60:5: error: missing binary operator before token "("
   60 | #if PTHREAD_STACK_MIN > 0
      |     ^~~~~~~~~~~~~~~~~

    "g++"   -fvisibility-inlines-hidden -fPIC -m64 -pthread -O3 -finline-functions -Wno-inline -Wall -fvisibility=hidden  -DBOOST_ALL_NO_LIB=1 -DBOOST_CHRONO_DYN_LINK=1 -DBOOST_SYSTEM_DYN_LINK=1 -DBOOST_THREAD_BUILD_DLL=1 -DBOOST_THREAD_POSIX -DBOOST_THREAD_USE_DLL=1 -DBOOST_TYPE_ERASURE_DYN_LINK -DNDEBUG  -I"." -c -o "bin.v2/libs/type_erasure/build/gcc-13.3.0/release/threadapi-pthread/threading-multi/visibility-hidden/dynamic_binding.o" "libs/type_erasure/src/dynamic_binding.cpp"

...failed gcc.compile.c++ bin.v2/libs/type_erasure/build/gcc-13.3.0/release/threadapi-pthread/threading-multi/visibility-hidden/dynamic_binding.o...
...skipped <pbin.v2/libs/type_erasure/build/gcc-13.3.0/release/threadapi-pthread/threading-multi/visibility-hidden>libboost_type_erasure.so.1.69.0 for lack of <pbin.v2/libs/type_erasure/build/gcc-13.3.0/release/threadapi-pthread/threading-multi/visibility-hidden>dynamic_binding.o...
...skipped <p/usr/local/lib>libboost_type_erasure.so.1.69.0 for lack of <pbin.v2/libs/type_erasure/build/gcc-13.3.0/release/threadapi-pthread/threading-multi/visibility-hidden>libboost_type_erasure.so.1.69.0...
...skipped <p/usr/local/lib>libboost_type_erasure.so for lack of <p/usr/local/lib>libboost_type_erasure.so.1.69.0...
...skipped <pbin.v2/libs/wave/build/gcc-13.3.0/release/threadapi-pthread/threading-multi/visibility-hidden>libboost_wave.so.1.69.0 for lack of <pbin.v2/libs/thread/build/gcc-13.3.0/release/threadapi-pthread/threading-multi/visibility-hidden>libboost_thread.so.1.69.0...
...skipped <p/usr/local/lib>libboost_wave.so.1.69.0 for lack of <pbin.v2/libs/wave/build/gcc-13.3.0/release/threadapi-pthread/threading-multi/visibility-hidden>libboost_wave.so.1.69.0...
...skipped <p/usr/local/lib>libboost_wave.so for lack of <p/usr/local/lib>libboost_wave.so.1.69.0...
...failed updating 12 targets...
...skipped 33 targets...
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
