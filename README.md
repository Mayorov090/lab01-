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
