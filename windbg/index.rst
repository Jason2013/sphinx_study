.. My Great Book documentation master file, created by
   sphinx-quickstart on Thu Mar 16 20:45:06 2017.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

WinDbg 经验技巧
=======================

.. .. toctree::
..    :maxdepth: 2
..    :caption: Contents:

..    cmake/index
..    ch01/index
..    ch02/index


LOG 文件设置
------------

- \.logopen

  打开一个日志文件，语法如下：

::

  .logopen [\t] [\u] [FileName]

  \t 附加进程 ID 和当前的日期、时间到日志文件名。这部分插入在文件名之后及文件名扩展之前。

  \u 用 Unicode 格式写入日志文件。如果省略该选项，调试器用 ASCII(ANSI) 格式写入日志文件。

