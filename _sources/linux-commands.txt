Linux 命令行工具
================

tar 命令
--------

分卷压缩
~~~~~~~~

1. 分卷压缩。
   
   注意split的参数 '-'(标准输出和输入), 生成的分包文件名为logs.tar.bz2.aa logs.tar.bz2.ab logs.tar.bz2.ac，以此类推。
   
   .. code-block:: bash
   
       tar jcf - logs/ | split -b 10m - logs.tar.bz2.

#. 解压缩命令为:
   
   .. code-block:: bash
   
       cat logs.tar.bz2.a* | tar xj -

创建 swap 文件
--------------

1. 创建一个 1G 大小的文件:
   
   .. code-block:: bash

       dd if=/dev/zero of=/root/swapfile bs=1024 count=1024000

#. 制作 swap 文件:

   .. code-block:: bash
       
       mkswap /root/swapfile

#. 让 swap 生效:

   .. code-block:: bash
       
       swapon /root/swapfile

#. 查看当前 swap:

   .. code-block:: bash
      
       swapon -s

#. 自动加载 swap。修改 /etc/fstab 加入下面的内容:

   .. code-block:: bash

       /root/swapfile swap swap defaults 0 1


