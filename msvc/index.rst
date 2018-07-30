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
