---
title: Redis持久化
date: 2022-5-26T9:00:00Z
lang: zh
duration: 10min
description: 就是两种，一种是RDB，一种是AOF
---


### RDB

rdb的全称为 Redis database backup file ,  也被称之为Redis的数据备份文件，简单的来说就是把Redis的所有的数据都备份都磁盘里面，当Redis出现了故障重启的时候就会自动的恢复数据。快照文件默认是保存到当前的目录位置

redis有自动的保存机制，设置在redis.conf中

```redis.conf
## 在900秒内,如果发生过一条数据的更新，那就使用gbsave保存数据,如果是save "" 则禁用高RDB
save 900 1
save 300 10
save 60 10000

# 是否压缩,一般建议不开启，压缩会消耗cpu资源
rdbcompression yes

## RBD文件名称
dbfilename dump.rdb

## 文件保存的路径目录
dir ./
```

## TODO，先咕咕咕，下次在写