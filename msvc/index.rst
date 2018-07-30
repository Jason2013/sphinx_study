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
