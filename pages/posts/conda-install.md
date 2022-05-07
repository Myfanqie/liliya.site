---
title: 动手深度学习-win环境安装
date: 2022-5-7T15:26:00Z
lang: zh
duration: 10min
description: 哎嘿~
---

### python配置镜像源加速

```bash
cd %APPDATA%    #切到appData目录下面
mkdir pip       #创建pip目录
```

![ea01adf921e14c534957d0a27969919b.png](https://img.gejiba.com/images/ea01adf921e14c534957d0a27969919b.png)
手动切换到这个目录下面创建一个pip.ini文件

文件里面就是这些，保存好就可以了

```ini
[global]
index-url = http://pypi.douban.com/simple
[install]
trusted-host=pypi.douban.com
```

### conda 基本操作

```bash
# 创建conda虚拟环境
conda create -n liliya_ai -y python=3.8 pip

# 选择conda虚拟环境
conda activate liliya_ai

# 如何退出conda虚拟环境
conda deactivate
```

### 安装依赖

启动上面的虚拟环境之后就可以了

```bash
pip install jupyter d2l torch torchvision
```

### 跑起来服务

先把上课要的笔记下载下来，解压笔记，然后切换到目录。
[https://zh-v2.d2l.ai/d2l-zh.zip](https://zh-v2.d2l.ai/d2l-zh.zip)

```bash
jupyter notebook
```

![1eceef5bddd5f2eb3fdb510b4e62abf7.png](https://img.gejiba.com/images/1eceef5bddd5f2eb3fdb510b4e62abf7.png)

![13757e1197c4fdc8c6f9ce34005c377c.png](https://img.gejiba.com/images/13757e1197c4fdc8c6f9ce34005c377c.png)

启动服务之后访问本地的有提示告诉你访问什么网址，这样就可以了。
