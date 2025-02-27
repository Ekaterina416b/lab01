# lab01


1. Скачайте библиотеку boost с помощью утилиты wget. Адрес для скачивания https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz.
```
~/workspace/tasks$ wget https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz
--2025-02-19 17:58:22--  https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz[task1.txt](https://github.com/user-attachments/files/18872750/task1.txt)
```
[task1](task1.txt)

2. Разархивируйте скаченный файл в директорию ~/boost_1_69_0
  ```
~/workspace/tasks$ tar -xzf boost_1_69_0.tar.gz -C ../../
```
3. Подсчитайте количество файлов в директории ~/boost_1_69_0 не включая вложенные директории.
```
~/boost_1_69_0$ find ~/boost_1_69_0 -maxdepth 1 -type f | wc -l
>12
```
4. Подсчитайте количество файлов в директории ~/boost_1_69_0 включая вложенные директории.
```
find ~/boost_1_69_0 -type f | wc -l
>61191
```
5. Подсчитайте количество заголовочных файлов, файлов с расширением .cpp, сколько остальных файлов (не заголовочных и не .cpp).
```
~/boost_1_69_0$ find ~/boost_1_69_0 -type f -name "*.hpp" | wc -l
>14912
~/boost_1_69_0$ find ~/boost_1_69_0 -type f -name "*.h" | wc -l
>296
~/boost_1_69_0$ find ~/boost_1_69_0 -type f -name "*.cpp" | wc -l
>13774
/boost_1_69_0$ find . -type f -not -name "*.cpp" -and -type f -not -name "*.hpp" -and -type f -not -name "*.h" | wc -l
>>32209
```
6. Найдите полный пусть до файла any.hpp внутри библиотеки boost.
```
~/boost_1_69_0$ find $(pwd) -name any.hpp
/home/ekaterina/boost_1_69_0/boost/spirit/home/support/algorithm/any.hpp
/home/ekaterina/boost_1_69_0/boost/any.hpp
/home/ekaterina/boost_1_69_0/boost/xpressive/detail/utility/any.hpp
/home/ekaterina/boost_1_69_0/boost/type_erasure/any.hpp
/home/ekaterina/boost_1_69_0/boost/fusion/algorithm/query/any.hpp
/home/ekaterina/boost_1_69_0/boost/fusion/algorithm/query/detail/any.hpp
/home/ekaterina/boost_1_69_0/boost/fusion/include/any.hpp
/home/ekaterina/boost_1_69_0/boost/proto/detail/any.hpp
/home/ekaterina/boost_1_69_0/boost/hana/fwd/any.hpp
/home/ekaterina/boost_1_69_0/boost/hana/any.hpp
```
7.Выведите в консоль все файлы, где упоминается последовательность boost::asio.
```
~/boost_1_69_0$ grep -rn . -e "boost::asio" > ../Рабочий\ стол/task7.txt
```
[task7](task7.txt)

8. Скомпилирутйе boost. Можно воспользоваться [инструкцией](https://www.boost.org/doc/libs/1_61_0/more/getting_started/unix-variants.html#or-build-custom-binaries) или [ссылкой](https://codeyarns.com/2017/01/24/how-to-build-boost-on-linux/).
```
~$ ./bootstrap.sh
~$ ./b2
~$ sudo ./b2 install
```
9. Перенесите все скомпилированные на предыдущем шаге статические библиотеки в директорию ~/boost-libs.
```
~/boost_1_69_0/stage/lib$ cp *.a ~/boost-libs/
~/boost-libs$ ls
```





    Перенесите все скомпилированные на предыдущем шаге статические библиотеки в директорию ~/boost-libs.
    Подсчитайте сколько занимает дискового пространства каждый файл в этой директории.
    Найдите топ10 самых "тяжёлых".
