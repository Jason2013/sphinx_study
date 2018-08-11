.. My Great Book documentation master file, created by
   sphinx-quickstart on Thu Mar 16 20:45:06 2017.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

Microsoft VC++ 经验技巧
=======================

.. .. toctree::
..    :maxdepth: 2
..    :caption: Contents:

..    cmake/index
..    ch01/index
..    ch02/index


禁用 LINK 的警告
-------------------

使用 ``/ignore:4221`` 选项，可以禁用 ``LINK 4221`` 警告。

在图形界面中，通过“Properties -> Linker -> Command Line”进行设置。

参考：
^^^^^^

- `Visual C++: How to disable specific linker warnings? <https://www.e-learn.cn/content/wangluowenzhang/402718>`_
- `(Stackoverflow) Visual C++: How to disable specific linker warnings? <https://stackoverflow.com/questions/661606/visual-c-how-to-disable-specific-linker-warnings>`_

Linker Tools Warning LNK4221
----------------------------

有如下两个 C++ 源文件：

a.cpp

.. code-block:: c++

    // a.cpp
    #include <atlbase.h>

b.cpp

.. code-block:: c++

    // b.cpp
    #include <atlbase.h>
    int func1()
    {
        return 0;
    }

先将源文件编译成目标文件：

::

    cl /c a.cpp b.cpp
    
当用如下命令行构建库的时候，会出现警告：

::

    link /lib /out:test.lib a.obj b.obj


当 a.cpp 与 b.cpp 中的 public symbol 有重复时，有下例 4 种情况，对构建库及应用的影响如下：

1. a.cpp 中的 public symbol 多于 b.cpp 中的，优先 b.obj 时：

   ::

     a
     a b
     a b

   链接库时，出现的警告信息如下：

   ::

     link /lib /out:test.lib a.obj b.obj
     a.obj : warning LNK4006: "int __cdecl func1(void)" (?func1@@YAHXZ) already defined in b.obj; second definition ignored

   当应用仅引用 a.cpp 和 b.cpp 中共同的符号时，将使用 b.cpp 中的符号，链接成功。

   ::

     link main.obj test.lib

   当应用引用 a.cpp 有而 b.cpp 中没有符号时，将引发如下错误：

   ::

     test.lib(a.obj) : error LNK2005: "int __cdecl func1(void)" (?func1@@YAHXZ) already defined in test.lib(b.obj)
     main.exe : fatal error LNK1169: one or more multiply defined symbols found

#. a.cpp 中的 public symbol 多于 b.cpp 中的，优先使用 a.obj 时：

   ::

       a
     b a
     b a

   链接库时，出现的警告信息如下：

   ::

     b.obj : warning LNK4006: "int __cdecl func1(void)" (?func1@@YAHXZ) already defined in a.obj; second definition ignored
     b.obj : warning LNK4221: This object file does not define any previously undefined public symbols, so it will not be used by any link operation that consumes this library

   应用将使用 a.cpp 中的符号，链接成功。


参考：
^^^^^^

- `Linker Tools Warning LNK4221 <https://msdn.microsoft.com/en-us/library/604bzebd.aspx>`_

- `What does LNK4221 mean? <https://blogs.msdn.microsoft.com/vcblog/2009/07/21/linker-warning-lnk4221-and-some-tips-to-avoid-it/>`_

- `How to eliminate Warning LNK4221? <https://stackoverflow.com/questions/20854324/how-to-eliminate-warning-lnk4221>`_

合并两个静态库
--------------

命令行如下：

::

    lib /OUT:filename.lib input1.lib input2.lib ...

参考：
^^^^^^

- `How do you combine static library files? <https://www.gamedev.net/forums/topic/475776-how-do-you-combine-static-library-files/>`_

- `[CMake] Merge two static libraries <https://cmake.org/pipermail/cmake/2010-October/040032.html>`_

- `Overview of LIB <https://msdn.microsoft.com/en-us/library/0xb6w1f8.aspx>`_
