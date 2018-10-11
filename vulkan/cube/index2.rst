.. My Great Book documentation master file, created by
   sphinx-quickstart on Thu Mar 16 20:45:06 2017.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

demo_build_image_ownership_cmd 函数
===================================

VkCommandBufferUsageFlags
-------------------------

* **VK_COMMAND_BUFFER_USAGE_ONE_TIME_SUBMIT_BIT** specifies that each recording of the command
  buffer will only be submitted once, and the command buffer will be reset and recorded again
  between each submission.

  指定 command buffer 中的每个 recording 只会被提交一次，在每个提交之间 command buffer 会重置并重新记录。

* **VK_COMMAND_BUFFER_USAGE_RENDER_PASS_CONTINUE_BIT** specifies that a secondary command buffer
  is considered to be entirely inside a render pass. If this is a primary command buffer, then this
  bit is ignored.

  指定 secondary command buffer 被认为完全位于 render pass 中。如果这是一个 primary command buffer ，那么这个标志位被忽略。

* **VK_COMMAND_BUFFER_USAGE_SIMULTANEOUS_USE_BIT** specifies that a command buffer can be
  resubmitted to a queue while it is in the pending state, and recorded into multiple primary
  command buffers.

.. .. toctree::
..    :maxdepth: 2
..    :caption: Contents:
.. 
..    cube/index
..    ch01/index
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
