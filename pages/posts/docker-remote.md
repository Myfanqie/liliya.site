---
title: docker远程连接，呜呜呜，电脑中毒了
date: 2022-5-25T15:40:00Z
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


## 所以为什么我中毒了

我就是按照了上面的操作，那么他们是怎么操作的。
下面这篇文章有介绍。。是如何通过Docker 2375 端口入侵服务器。
[http://www.dockerinfo.net/1416.html](http://www.dockerinfo.net/1416.html)

#### 大概就是分为以下几步，

第一步就是扫描ip网段，从网上下载了腾讯云，阿里云这些的ip地址网段，然后一个个的扫描2375端口。
第二步发现了可以远程连接的docker服务之后，就测试2375的直接控制权限
第三步远程启动自己的容器
第四步ssh pub key注入，允许root通过ssh登录，
第五步想干嘛就干嘛了。


## 所以应该怎么防范

就像这样，不使用软件的默认端口，docker就不使用2375端口了，而是换一个像是2376这种。

```bash
-H tcp://0.0.0.0:2376 -H unix://var/run/docker.sock
```

参考链接 [远程连接docker daemon，Docker Remote API](https://deepzz.com/post/dockerd-and-docker-remote-api.html)