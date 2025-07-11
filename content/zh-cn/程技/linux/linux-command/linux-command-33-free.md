---
title: '每天一个linux命令（33）: free'
date: 2017-01-02 21:43:26
type: posts
cover: https://jsd.cdn.zzko.cn/gh/richbridge/picx-images-hosting@master/thumbnail/程技.jpg
categories: [程技]
tags: ["linux命令"]
---
　　free命令可以显示Linux系统中空闲的、已用的物理内存及swap内存,及被内核使用的buffer。在Linux系统监控的工具中，free命令是最经常使用的命令之一。
<!--more -->
#### 命令格式
```bash
$ free [参数]
```
#### 命令功能
　　free 命令显示系统使用和空闲的内存情况，包括物理内存、交互区内存(swap)和内核缓冲区内存。共享内存将被忽略
<!--more -->
#### 命令参数
| 命令 | 描述     |
| :------------- | :------------- |
| -b | 以Byte为单位显示内存使用情况  |
| -k | 以KB为单位显示内存使用情况 |
| -m | 以MB为单位显示内存使用情况 |
| -g | 以GB为单位显示内存使用情况 |
| -o | 不显示缓冲区调节列 |
| -s<间隔秒数> | 持续观察内存使用状况 |
| -t  | 显示内存总和列 |
| -V | 显示版本信息 |
#### 使用实例
**`例一`：显示内存使用情况**
```bash
$ free
              total        used        free      shared  buff/cache   available
Mem:       12095180     8362640      198460     1379116     3534080     2100004
Swap:       8185112       40008     8145104
```
>**说明：**
total:总计物理内存的大小。
used:已使用多大。
free:可用有多少。
Shared:多个进程共享的内存总额。
Buffers/cached:磁盘缓存的大小。

**`例二`：显示内存使用情况**
```bash
$ free -t
```
**`例三`：周期性的查询内存使用信息**
```bash
## 每10s 执行一次命令
$ free -s 10
```
