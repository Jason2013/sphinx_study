.. My Great Book documentation master file, created by
   sphinx-quickstart on Thu Mar 16 20:45:06 2017.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

Grapher 介绍
===============

.. toctree::
   :maxdepth: 2
   :caption: Contents:

相关文件介绍
------------

   ``${ROOT}\phplibs\generalLibs\code01.php``

   基本信息配置文件，包含：数据库连接信息。

   ``phplibs/userManage/swtUserManager.php``

   用户及管理员信息类型。调试阶段，建议将 ``isManager()`` 设为始终返回 ``true`` 。

   调试报告生成时，需要将服务器上的 logStore 目录下该批次的目录，复制到本机的 logStore 目录下，以进行调试。
   “目录名称”与“批次号”的对应关系如下：

.. code-block:: sql

    select *
    from mis_table_batch_list b left join mis_table_path_info p on b.path_id = p.path_id
    where b.batch_id = 1071;
