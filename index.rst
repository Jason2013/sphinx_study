.. My Great Book documentation master file, created by
   sphinx-quickstart on Thu Mar 16 20:45:06 2017.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

.. _chapter:

Welcome to My Great Book's documentation!
=========================================

.. toctree::
   :maxdepth: 3
   :caption: 目录
   :numbered:

   oglp/index
   cmake/index
   msvc/index
   example/index
   cpp/index
   vulkan/index
   windbg/index
   links

我是一级标题
============

我是正文。添加一些描述性的文字。

Welcome to My Great Book's documentation!
-----------------------------------------

我是二级标题
------------

*Welcome* to **My** ``Great`` Book's documentation!

欢迎光临 `网易新闻 <http://news.163.com>`_ ！

.. _网易新闻 link: http://news.163.com

A欢迎光临 `网易新闻`_ ！
A欢迎光临 `网易新闻`_ ！
b欢迎光临\ `网易新闻`_！

.. _网易新闻: http://news.163.com

.. this is `a lin`_. ！

.. .. _a lin link: http://news.163.com

this is a paragraph that contains `a link`_.

.. _a link: https://domain.invalid/

Welcome to My Great Book's documentation!
-----------------------------------------

goto :ref:`chapter`.

跳转到一个文件：:doc:`msvc/index` ，点击试一试。

See :download:`This is an example <src/main.cpp>` 。

ENVAR :envvar:`DK_ROOT`

Since Pythagoras, we know that :math:`a^2 + b^2 = c^2`.

:kbd:`Control-x Control-f`

:menuselection:`Start --> Programs`

Release |release|

Version |version|

Today is |today|

.. DANGER::
   Beware killer rabbits!

.. danger::
   Beware killer rabbits!

.. attention::
   Beware killer rabbits!

.. caution::
   Beware killer rabbits!

.. note::
   Beware killer rabbits!

.. hint::
   Beware killer rabbits!

.. important::
   Beware killer rabbits!

.. tip::
   Beware killer rabbits!

.. warning::
   Beware killer rabbits!

.. versionadded:: 1.1.0
   Beware killer rabbits!

.. versionchanged:: 1.2.0
   Beware killer rabbits!

.. deprecated:: 1.3.0
   Beware killer rabbits!

.. seealso::

   Module :py:mod:`zipfile`
      Documentation of the :py:mod:`zipfile` standard module.

   `GNU tar manual, Basic Tar Format <http://link>`_
      Documentation for tar archive files, including GNU tar extensions.

.. centered:: LICENSE AGREEMENT

Running the program needs a license.

.. py:function:: spam(eggs)
                 ham(eggs)

   Spam or ham the foo.

.. py:function:: filterwarnings(action, message='', category=Warning, \
                                module='', lineno=0, append=False)
   :noindex:

请参考： :ref:`merge_libs`

Indices and tables
==================

* :ref:`genindex`
* :ref:`modindex`
* :ref:`search`
