---
title: 原神，体验飞一般的感觉
date: 2022-5-01T16:00:00Z
lang: zh
duration: 10min
description: 这个教程尽可能的简单来
---


## 前言

先来点废话，如果没有任何IT基础也不会使用搜索引擎的话，建议立刻退出去。

## 环境搭建前提

这个教程不是官服的，是参考的第三方blog的，所以配置也不是按照官方的来。

[JDK17](https://www.oracle.com/java/technologies/downloads/#jdk17-windows) <br>
[MongoDB](https://www.runoob.com/mongodb/mongodb-window-install.html) <br>
[Fidder](http://www.downza.cn/soft/234727.html) 这里我用的中文版的 <br>
[Python3.8+](https://www.python.org/downloads/) 直接干最新版的。

## server端的搭建和启动

1. 下载服务端源文件，这里放到百度网盘了
链接：[https://pan.baidu.com/s/1cgmGXbSpBvM7wTmLiTA83Q](https://pan.baidu.com/s/1cgmGXbSpBvM7wTmLiTA83Q)
提取码：2333

2. 解压密码是`blog.tomys.top`

3. 解压之后 ![解压图片](https://img.gejiba.com/images/dce2f5279b95c0b62cbf81a88fa79e97.png)

4. 修改run.bat为自己的jdk17的地址 ![解压图片](https://img.gejiba.com/images/03d4575c4a548ea0dca3cb0c624c2712.png)

5. 双击启动 [![cbc9970f677a6ed0d0744767114c021b.md.png](https://img.gejiba.com/images/cbc9970f677a6ed0d0744767114c021b.md.png)](https://img.gejiba.com/image/M5Z3s)

## fiddler代理流量

1. 工具->选项-> https 选中这两个 [![c2e7bf92a72b5cfe970c5840c8f4837a.md.png](https://img.gejiba.com/images/c2e7bf92a72b5cfe970c5840c8f4837a.md.png)](https://img.gejiba.com/image/M5h9i)

2. 连接->这些都√上，然后端口监听54321 [![103ec51da950be7305dbdbd59789c478.md.png](https://img.gejiba.com/images/103ec51da950be7305dbdbd59789c478.md.png)](https://img.gejiba.com/image/M5rL1)

3. 记得要勾选上启动的时候充当系统代理 [![d306b0273d30166306538ac7604e19d9.md.png](https://img.gejiba.com/images/d306b0273d30166306538ac7604e19d9.md.png)](https://img.gejiba.com/image/M5zlz)

4. 添加一个脚本到fiddlerscript里面

这里的脚本就是为了充当中间人代理mihoyo的流量,这下面的脚本要放到 `OnBeforeRequest` 这个函数下面才行。

```java
import System.Text.RegularExpressions;
```

```java
if(oSession.host.EndsWith(".yuanshen.com") || oSession.host.EndsWith(".hoyoverse.com") || oSession.host.EndsWith(".mihoyo.com")) {
            oSession.host = "localhost"; // This can also be replaced with another IP address.
}
```

[![9844f9bc09b7a270935c73c030f7bf93.md.png](https://img.gejiba.com/images/9844f9bc09b7a270935c73c030f7bf93.md.png)](https://img.gejiba.com/image/M5kI5)

[![2ec1442171c7c612371f6e3367a6315e.md.png](https://img.gejiba.com/images/2ec1442171c7c612371f6e3367a6315e.md.png)](https://img.gejiba.com/image/M5big)

## 启动原神

过了新手教程之后，就可以和server机器人私聊发送命令，发送`/hlep`来获取各种命令的使用方法

注意：命令必须带`/`

[![10318d0452cc8c4d7a4481b5d8e9bdbb.md.png](https://img.gejiba.com/images/10318d0452cc8c4d7a4481b5d8e9bdbb.md.png)](https://img.gejiba.com/image/M5Hby)

[![d957e4dbc0eb6721bf24c17e369d39a7.md.png](https://img.gejiba.com/images/d957e4dbc0eb6721bf24c17e369d39a7.md.png)](https://img.gejiba.com/image/M5vZB)

### 创建角色

在控制台输入 `account create [角色名] [uid]`

[![2651eba6258fa6cf0bc5f4b3789edccf.md.png](https://img.gejiba.com/images/2651eba6258fa6cf0bc5f4b3789edccf.md.png)](https://img.gejiba.com/image/M50Uv)

## 参考链接

官方的github的链接 [https://github.com/Grasscutters/Grasscutter](https://github.com/Grasscutters/Grasscutter) <br>
这个服务端提供的blog链接 [https://blog.tomys.top/2022-04/GenshinTJ/](https://blog.tomys.top/2022-04/GenshinTJ/)
