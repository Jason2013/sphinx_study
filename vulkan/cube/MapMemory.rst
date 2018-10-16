.. My Great Book documentation master file, created by
   sphinx-quickstart on Thu Mar 16 20:45:06 2017.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

Host Access to Device Memory Objects
====================================

.. .. toctree::
..    :maxdepth: 2
..    :caption: Contents:
.. 
..    index2
..    index3

Memory objects created with ``vkAllocateMemory`` are not directly host accessible.

由 ``vkAllocateMemory`` 创建的 Memory object 并不是直接 host accessiable 。

Memory objects created with the memory property ``VK_MEMORY_PROPERTY_HOST_VISIBLE_BIT`` are
considered mappable. Memory objects must be mappable in order to be successfully mapped on
the host.

创建 Memory objects 时指定了 memory 属性 ``VK_MEMORY_PROPERTY_HOST_VISIBLE_BIT`` 被认为是可映射的（ mappable ）。要能够成功映射到 host ， Memory object 必须是可映射的。

To retrieve a host virtual address pointer to a region of a mappable memory object, call

要获取一个指向可映射 memory object 的 host 虚拟地址指针，调用：

.. code-block: cpp

   VkResult vkMapMemory(
       VkDevice          device,
       VkDeviceMemory    memory,
       VkDeviceSize      offset,
       VkDeviceSize        size,
       VkMemoryMapFlags   flags,
       void**           ppData);

``vkMapMemory`` does not check whether the device memory is currently in use before returning the
host-accessible pointer. The application must guarantee that any previously submitted command
that writes to this range has completed before the host reads from or writes to that range, and that
any previously submitted command that reads from that range has completed before the host
writes to that region (see here for details on fulfilling such a guarantee). If the device memory was
allocated without the ``VK_MEMORY_PROPERTY_HOST_COHERENT_BIT`` set, these guarantees must be made for
an extended range: the application must round down the start of the range to the nearest multiple
of ``VkPhysicalDeviceLimits::nonCoherentAtomSize``, and round the end of the range up to the nearest
multiple of ``VkPhysicalDeviceLimits::nonCoherentAtomSize``.

While a range of device memory is mapped for host access, the application is responsible for
synchronizing both device and host access to that memory range.

.. Vulkan Cube 简介
.. ----------------
.. 
.. Vulkan cube 是 Vulkan SDK 中附带的示例程序，用来演示 Vulkan SDK 的使用方法。

..    ch02/index

.. The function :py:func:`spam` does a similar thing.
.. 
.. 静态网页生成器
.. ==============
.. 
.. 常用的静态网页生成器有如下几个：
.. 
.. * `jellky <https://jekyllrb.com/>`_
.. * `Hugo <https://gohugo.io/>`_
.. * `Hexo <https://hexo.io/>`_
.. * `pelican <https://blog.getpelican.com/>`_
.. * `Hyde <http://hyde.github.io>`_
.. 
.. :jellky: 基于 Ruby 开发，是 github pages 的默认页面生成器。
.. 
.. :Hugo: 基于 Go 语言开发，生成页面速度较快。
.. 
.. :Hexo: 生成页面速度较快，支持 Markdown 和 Octopress 插件。
.. 
.. :pelican: 基于 Python 开发，默认支持 reStructuredText ，通过插件支持 Markdown 。
.. 
.. :Hyde: 基于 Python 开发，有评论说文档支持不够友好。
