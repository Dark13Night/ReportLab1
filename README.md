# ReportLab1

# 1. Скачайте библиотеку boost с помощью утилиты wget. Адрес для скачивания https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz

$ wget https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz

# 2. Разархивируйте скаченный файл в директорию ~/boost_1_69_0

$ tar -xvf boost_1_69_0.tar.gz

# работаем в ~/boost_1_69_0

# 3. Подсчитайте количество файлов в директории ~/boost_1_69_0 не включая вложенные директории

$ ls -l | grep "^-" | wc -l

# 4. Подсчитайте количество файлов в директории ~/boost_1_69_0 включая вложенные директории.

$ ls -l -R | wc -l

# 5. Подсчитайте количество заголовочных файлов, файлов с расширением .cpp, сколько остальных файлов (не заголовочных и не .cpp).

$ ls -l -R | grep -c *.hpp
$ ls -l -R | grep -c *.cpp
$ ls -l -R | grep -v *.hpp | grep -v *.cpp | grep -v 'итого' | wc -l

# 6. Найдите полный пусть до файла any.hpp внутри библиотеки boost.

$ find $PWD -type f -name any.hpp

# 7. Выведите в консоль все файлы, где упоминается последовательность boost::asio

$ grep -R -l "boost::asio"

# 8. Скомпилирутйе boost. Можно воспользоваться инструкцией или ссылкой.

$ ./bootstrap.sh --prefix=boost_output
$ ./b2 install

# 9. Перенесите все скомпилированные на предыдущем шаге статические библиотеки в директорию ~/boost-libs.

$ mv ~/boost_1_69_0/boost_output/lib ~/boost-libs

# 10. Подсчитайте сколько занимает дискового пространства каждый файл в этой директории.

$ du -h -a 

# 11. Найдите топ10 самых "тяжёлых".

$ du -h -a | sort -r -h | head -n 10



# References used
