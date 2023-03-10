# ReportLab1

## 1. Скачайте библиотеку boost с помощью утилиты wget. Адрес для скачивания https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz
```
$ wget https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz
```
![X9_5iPaTKpQ](https://user-images.githubusercontent.com/112771541/224356253-74733aa3-2421-475f-b2da-a4380014b30c.jpg)

## 2. Разархивируйте скаченный файл в директорию ~/boost_1_69_0
```
$ tar -xvf boost_1_69_0.tar.gz
```
![Ojjnk4tcYBA](https://user-images.githubusercontent.com/112771541/224356321-a6ff0038-3c41-4f48-ac2f-6251ea86d367.jpg)

дальше работаем в ~/boost_1_69_0

![DBpVnMK4C8Y](https://user-images.githubusercontent.com/112771541/224357592-fa0b96e5-de11-4c94-b481-19149ada800a.jpg)


## 3. Подсчитайте количество файлов в директории ~/boost_1_69_0 не включая вложенные директории
```
$ ls -l | grep "^-" | wc -l
```
## 4. Подсчитайте количество файлов в директории ~/boost_1_69_0 включая вложенные директории.
```
$ ls -l -R | wc -l
```
![54D8x2naQjo](https://user-images.githubusercontent.com/112771541/224356536-503309f0-1596-4342-b48b-a4df976b2179.jpg)

## 5. Подсчитайте количество заголовочных файлов, файлов с расширением .cpp, сколько остальных файлов (не заголовочных и не .cpp).
```
$ ls -l -R | grep -c *.hpp
$ ls -l -R | grep -c *.cpp
$ ls -l -R | grep -v *.hpp | grep -v *.cpp | grep -v 'итого' | wc -l
```
![ISi8796XQTc](https://user-images.githubusercontent.com/112771541/224356753-0031aaae-8e2e-4a46-a730-1ac0cf7958d9.jpg)

![image](https://user-images.githubusercontent.com/112771541/224358352-6e8c6fd5-360e-484d-b577-cf7732a5760f.png)



## 6. Найдите полный пусть до файла any.hpp внутри библиотеки boost.
```
$ find $PWD -type f -name any.hpp
```
![hsprs1-9XrE](https://user-images.githubusercontent.com/112771541/224356860-391d8510-1d56-4e7c-86b3-2054a9bf5882.jpg)

## 7. Выведите в консоль все файлы, где упоминается последовательность boost::asio
```
$ grep -R -l "boost::asio"
```

![VCKUnrHlozA](https://user-images.githubusercontent.com/112771541/224356931-d484ecb5-3a19-469b-a100-7a3137274659.jpg)

## 8. Скомпилирутйе boost. Можно воспользоваться инструкцией или ссылкой.
```
$ ./bootstrap.sh --prefix=boost_output
$ ./b2 install
```
![oZGsp3-2Guo](https://user-images.githubusercontent.com/112771541/224357086-dfe8d54e-5a45-4fd0-a59f-7278bd1dc2e8.jpg)

## 9. Перенесите все скомпилированные на предыдущем шаге статические библиотеки в директорию ~/boost-libs.
```
$ mv ~/boost_1_69_0/boost_output/lib ~/boost-libs
```
![x9kS2g3FP_k](https://user-images.githubusercontent.com/112771541/224357344-ae5289d0-97b3-4e66-859b-baa7e12043df.jpg)

## 10. Подсчитайте сколько занимает дискового пространства каждый файл в этой директории.
```
$ du -h -a 
```

![image](https://user-images.githubusercontent.com/112771541/224357709-66952c89-0fa5-4a2b-b2ae-bbccbc4a2d9b.png)


## 11. Найдите топ10 самых "тяжёлых".
```
$ du -h -a | sort -r -h | head -n 10
```

![image](https://user-images.githubusercontent.com/112771541/224357991-d7381317-a3cc-4365-99f7-93375c15b236.png)

