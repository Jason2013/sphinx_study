.. My Great Book documentation master file, created by
   sphinx-quickstart on Thu Mar 16 20:45:06 2017.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

C++ 经验技巧
=======================

.. .. toctree::
..    :maxdepth: 2
..    :caption: Contents:

..    cmake/index
..    ch01/index
..    ch02/index


C++ 读写二进制文件
------------------

读取一个二进制文件，并写入另外一个二进制文件：

.. code-block:: cpp

   #include <fstream>
   #include <iterator>
   #include <algorithm>
   
   int main()
   {
       std::ifstream input( "C:\\Final.gif", std::ios::binary );
       std::ofstream output( "C:\\myfile.gif", std::ios::binary );
   
       std::copy( 
           std::istreambuf_iterator<char>(input), 
           std::istreambuf_iterator<char>( ),
           std::ostreambuf_iterator<char>(output));
   }

将二进制文件读入内存，用于后续处理：

.. code-block:: cpp

   #include <fstream>
   #include <iterator>
   #include <vector>
   
   int main()
   {
       std::ifstream input( "C:\\Final.gif", std::ios::binary );
       // copies all data into buffer
       std::vector<char> buffer((
               std::istreambuf_iterator<char>(input)), 
               (std::istreambuf_iterator<char>()));
   }

参考：
^^^^^^

- `Reading and writing binary file <https://stackoverflow.com/questions/5420317/reading-and-writing-binary-file>`_
- `C++ Binary File I/O <http://courses.cs.vt.edu/~cs2604/fall00/binio.html>`_
- `C++ Programming Examples <https://codescracker.com/cpp/program/cpp-programming-examples.htm>`_

typedef 定长数组
----------------

想定义一个 3 字节的数组为一个新的类型，方法如下：

.. code-block:: cpp

   typedef char[3] type24;

但编译不通过。

正确的做法如下：

.. code-block:: cpp

   typedef char type24[3];

However, this is probably a very bad idea, because the resulting type is an array type, but users of it won't see that it's an array type. If used as a function argument, it will be passed by reference, not by value, and the ``sizeof`` for it will then be wrong.

A better solution would be

.. code-block:: cpp

   typedef struct type24 { char x[3]; } type24;

You probably also want to be using ``unsigned char`` instead of ``char``, since the latter has implementation-defined signedness.   

参考：
^^^^^^

- `typedef fixed length array <https://stackoverflow.com/questions/4523497/typedef-fixed-length-array>`_
