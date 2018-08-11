.. My Great Book documentation master file, created by
   sphinx-quickstart on Thu Mar 16 20:45:06 2017.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

CMake 经验技巧
==============

.. .. toctree::
..    :maxdepth: 2
..    :caption: Contents:

..    cmake/index
..    ch01/index
..    ch02/index


target 的 TYPE 属性
-------------------

target 的 ``TYPE`` 属性为“只读”，不可以更改。

参考：
^^^^^^
- `TYPE <https://cmake.org/cmake/help/v3.12/prop_tgt/TYPE.html>`_

add_custom_target 的技巧
---------------------

自定义 ``target`` 被认为总是过期，即使它有生成文件。因此，自定义 ``target`` 总是会被生成。


参考：
^^^^^^
- `TYPE <https://cmake.org/cmake/help/v3.12/command/add_custom_target.html>`_
