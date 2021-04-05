# lab01
```
1)Скачайте библиотеку boost с помощью утилиты wget. Адрес для скачивания https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz.

команда: wget https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz
```
```
2)Разархивируйте скаченный файл в директорию ~/boost_1_69_0

команда: tar -zxvf boost_1_69_0.tar.gz
```
```
3)Подсчитайте количество файлов в директории ~/boost_1_69_0 не включая вложенные директории.

команда: find boost_1_69_0 -maxdepth 1 -type f | wc
результат: 12
```
```
4)Подсчитайте количество файлов в директории ~/boost_1_69_0 включая вложенные директории.

команда: find boost_1_69_0 -type f | wc -l
результат: 61191
```
```
5)Подсчитайте количество заголовочных файлов, файлов с расширением .cpp, сколько остальных файлов (не заголовочных и не .cpp).

заголовочные - find boost_1_69_0 -type f -name "*.h" | wc    (296)
.cpp - find. -type f -name "*.cpp" | wc   (13774)    
остальные - find boost_1_69_0 -type f -not -name "*.cpp" -not -name "*.h" | wc    (47121)
```
```
6)Найдите полный пусть до файла any.hpp внутри библиотеки boost.

команда: realpath any.hpp
результат: /home/ser4ik/any.hpp
```
```
7)Выведите в консоль все файлы, где упоминается последовательность boost::asio.
 
команда: grep -lR "boost::asio"
кусочек вывода:
boost_1_69_0/boost/process/detail/async_handler.hpp
boost_1_69_0/boost/process/detail/posix/sigchld_service.hpp
boost_1_69_0/boost/process/detail/posix/io_context_ref.hpp
boost_1_69_0/boost/process/detail/posix/async_pipe.hpp
boost_1_69_0/boost/process/detail/posix/async_in.hpp
boost_1_69_0/boost/process/detail/posix/async_out.hpp
boost_1_69_0/boost/log/sinks/syslog_backend.hpp
Mayorov/workspace/tasks/lab01/README.md
Mayorov/workspace/reports/lab01/.REPORT.md.swp
Mayorov/workspace/reports/lab01/REPORT.md
```
```
8)Скомпилируйте boost. Можно воспользоваться инструкцией или ссылкой.

команды:
sudo apt install libicu-dev
./bootstrap.sh --prefix=boost_output
./b2 install -j 8
```
```
9)Перенесите все скомпилированные на предыдущем шаге статические библиотеки в директорию ~/boost-libs.

команды:
mkdir -p ./boost-libs
mv ~/boost_1_69_0/boost_output/lib/* ~/boost-libs/
result:
0	//snap/core18/1885/var/spool
0	//snap/core18/1885/var/tmp
143K	//snap/core18/1885/var
0	//snap/core18/1885/writable
169M	//snap/core18/1885
169M	//snap/core18
1.6G	//snap
8.9G	//

```
```
10)Подсчитайте сколько занимает дискового пространства каждый файл в этой директории.
command: ncdu
result:
 4.4 MiB [##########]  libboost_wave.a                                       
    4.2 MiB [######### ]  libboost_log.a
    3.3 MiB [#######   ]  libboost_locale.a
    3.0 MiB [######    ]  libboost_math_tr1.a
    3.0 MiB [######    ]  libboost_math_tr1l.a
    3.0 MiB [######    ]  libboost_math_tr1f.a
    2.9 MiB [######    ]  libboost_regex.a
```
```
11)Найдите топ10 самых "тяжёлых".
command: du -ah | sort -rh | head -10 
result:
52M	.
4.4M	./libboost_wave.a
4.3M	./libboost_log.a
3.4M	./libboost_locale.a
3.1M	./libboost_math_tr1l.a
3.1M	./libboost_math_tr1.a
3.0M	./libboost_regex.a
3.0M	./libboost_math_tr1f.a
2.6M	./libboost_log_setup.a
2.4M	./libboost_test_exec_monitor.a
```














