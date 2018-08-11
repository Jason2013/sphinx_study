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

CMAKE_TOOLCHAIN_FILE was not used by the project
------------------------------------------------

用 CMake 构建工程文件时，会出现如下警告信息：

::

  CMake Warning:
    Manually-specified variables were not used by the project:

      CMAKE_TOOLCHAIN_FILE

This is the standard warning gives you when you're giving it a command line option it's not using. That is giving -DFOO=bar to cmake when the CMakeLists.txt doesn't use FOO variable.

Now, that's a bit of a special case here: CMAKE_TOOLCHAIN_FILE is used by CMake the first time you're configuring your build, but as you can't change the toolchain for an already configured build, it's ignored every other time, thus the warning.


参考：
^^^^^^
- `CMAKE_TOOLCHAIN_FILE was not used by the project <https://stackoverflow.com/questions/14757506/cmake-toolchain-file-was-not-used-by-the-project>`_

add_custom_target 的技巧
---------------------

自定义 ``target`` 被认为总是过期，即使它有生成文件。因此，自定义 ``target`` 总是会被生成。

自定义 ``target`` 的 ``TYPE`` 为 ``UTILITY`` ，无法将其做为某个应用的依赖库，如： ``target_link_libraries(target <user_defined_target>)`` 。

参考：
^^^^^^
- `add_custom_target <https://cmake.org/cmake/help/v3.12/command/add_custom_target.html>`_
