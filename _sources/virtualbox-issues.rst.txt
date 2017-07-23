Virtualbox 相关话题
===================

Virtualbox 虚拟磁盘文件的压缩
------------------------------

1. 虚拟磁盘碎片整理。在虚拟机中执行如下命令:

   .. code-block:: bash 

       sudo dd if=/dev/zero of=/EMPTY bs=1M
       sudo rm -f /EMPTY

2. 压缩磁盘。关闭虚拟机，在宿主机中执行下面的命令:
   
   .. code-block:: bash

       VBoxManage modifyhd mydisk.vdi --compact

参考资料:
    `如何减小VirtualBox虚拟硬盘文件的大小 <https://my.oschina.net/tsl0922/blog/188276>`_

