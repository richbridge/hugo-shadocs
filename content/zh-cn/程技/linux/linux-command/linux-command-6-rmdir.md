---
title: '每天一个linux命令（6）: rmdir'
date: 2016-12-06 15:24:32
type: posts
cover: https://jsd.cdn.zzko.cn/gh/richbridge/picx-images-hosting@master/thumbnail/程技.jpg
categories: [程技]
tags: ["linux命令"]
---
　　今天学习一下linux中命令： rmdir命令。rmdir是常用的命令，该命令的功能是删除空目录，一个目录被删除之前必须是空的。（注意，rm - r dir命令可代替rmdir，但是有很大危险性。）删除某目录时也必须具有对父目录的写权限。
<!--more -->
#### 命令格式
```bash
$ rmdir [选项]... 目录...
```
#### 命令功能
　　该命令从一个目录中删除一个或多个子目录项，删除某目录时也必须具有对父目录的写权限。
#### 命令参数
| 参数     | 描述     |
| :------------- | :------------- |
| - p       | 递归删除目录dirname，当子目录删除后其父目录为空时，也一同被删除。如果整个路径被删除或者由于某种原因保留部分路径，则系统在标准输出上显示相应的信息      |
| -v, --verbose      | 显示指令执行过程        |
#### 命令实例
**`例一`：rmdir 不能删除非空目录**
```bash
$ rmdir doc
rmdir: doc: 目录非空
```
**`例二`：rmdir -p 当子目录被删除后使它也成为空目录的话，则顺便一并删除**
```bash
$ rmdir -p log/product
```
