Python 编码相关问题收集
=======================

PYTHONIOENCODING 环境变量
-------------------------

python 脚本重定向到文件遭遇 UnicodeDecodeError 时需要设置环境变量 PYTHONIOENCODING, 可以在 .bashrc 中加入如下内容::

    export PYTHONIOENCODING=UTF-8


requests 库中的编码问题
-----------------------

`requests <https://github.com/kennethreitz/requests>`_ 通过 http header 信息来确定网页的编码信息，如果编码信息不存在就会默认为 ISO-8859-1，当 http header 中不包含编码信息时会发生乱码。

其实 requests 库中已经包含了猜测编码的功能。我们可以在访问 ``r.text`` 属性之前设置 ``r.encoding = r.apparent_encoding`` 来设置正确的页面编码。

