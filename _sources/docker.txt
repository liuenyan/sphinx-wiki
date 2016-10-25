Docker 配置
===========

Arch Linux 下设置 DockerHub 镜像
--------------------------------

创建配置文件重写 systemd 的 docker.service 的默认配置::

    mkdir -p /etc/systemd/system/docker.service.d
    cd /etc/systemd/system/docker.service.d/
    vim my.conf

在 my.conf 中重写 ExecStart, 加入网易蜂巢的 docker 加速镜像::
    
    [Service]
    ExecStart=
    ExecStart=/usr/bin/dockerd -H fd:// --registry-mirror="http://hub-mirror.c.163.com"

重启 docker 服务::

    systemctl daemon-reload
    systemctl restart docker.service

