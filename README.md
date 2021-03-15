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
./b2 install
```
```
9)Перенесите все скомпилированные на предыдущем шаге статические библиотеки в директорию ~/boost-libs.

команды:















