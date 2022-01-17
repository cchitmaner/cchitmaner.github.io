---
title: linux更改udp、tcp缓冲区大小
date: 2022-1-17 10:50:00
tags:

categories:

toc: true # 是否开启内容索引

sidebar: none # 是否启用sidebar侧边栏，none：不启用

---

## 一、系统设置

```
[jiang@localhost ~]$ uname -a
Linux localhost.localdomain 2.6.32-642.el6.x86_64 #1 SMP Tue May 10 17:27:01 UTC 2016 x86_64 x86_64 x86_64 GNU/Linux
[jiang@localhost ~]$ cat /proc/sys/net/core/rmem_max
124928
[jiang@localhost ~]$ cat /proc/sys/net/core/wmem_max
124928
[jiang@localhost ~]$ cat /proc/sys/net/core/rmem_default
124928
[jiang@localhost ~]$ cat /proc/sys/net/core/wmem_default
124928
```

rmem_max：一个Socket的读缓冲区可由程序设置的最大值，单位字节；
wmem_max：一个Socket的写缓冲区可由程序设置的最大值，单位字节；
rmem_default：一个Socket的被创建出来时，默认的读缓冲区大小，单位字节；
wmem_default：一个Socket的被创建出来时，默认的写缓冲区大小，单位字节；

注：/proc是一个很特殊的文件系统，其并非真实存在于物理磁盘，而是当前系统运行状态的一个映射，存在于RAM中。

## 二、系统级修改缓冲区大小

```
[root@localhost ~]# echo 262144 > /proc/sys/net/core/rmem_default
[root@localhost ~]# echo 1048576 > /proc/sys/net/core/rmem_max
```

