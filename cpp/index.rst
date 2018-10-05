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
