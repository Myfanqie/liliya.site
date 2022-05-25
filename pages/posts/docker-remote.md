---
title: docker远程连接
date: 2022-5-257T15:40:00Z
lang: zh
duration: 5min
description: 服务器中毒了呜呜呜
---

> 服务器不知道怎么中挖矿病毒了，真的不知道怎么办，就重装了。呜呜呜

![docker添加远程](../../img/assets/bingdu.png)

1. 编辑这个文件
/lib/systemd/system/docker.service

2. 加上 `-H tcp://0.0.0.0:2375 -H unix://var/run/docker.sock`
如图

![docker添加远程](../../img/assets/img-20220525docker.png)

3. 重新加载配置文件并重启docker：

```bash
systemctl daemon-reload && systemctl restart docker

```
