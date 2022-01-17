---
title: 更改pip源至国内镜像，显著提升下载速度
---

## 临时使用

在使用pip的时候加参数-i https://pypi.tuna.tsinghua.edu.cn/simple

例如：pip install -i https://pypi.tuna.tsinghua.edu.cn/simple gevent，这样就会从清华这边的镜像去安装gevent库。

## 永久修改

1. linux下，修改 ~/.pip/pip.conf (没有就创建一个)， 修改 index-url至tuna，内容如下：

   ```
    [global]
    index-url = https://pypi.tuna.tsinghua.edu.cn/simple
   ```

2. windows下，直接在user目录中创建一个pip目录，如：C:\Users\xx\pip，新建文件pip.ini，内容如下

   ```
    [global]
    index-url = https://pypi.tuna.tsinghua.edu.cn/simple
   ```