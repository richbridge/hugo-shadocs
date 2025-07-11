---
title: '每天一个linux命令（14）: head'
date: 2016-12-14 14:35:49
type: posts
cover: https://jsd.cdn.zzko.cn/gh/richbridge/picx-images-hosting@master/thumbnail/程技.jpg
categories: [程技]
tags: ["linux命令"]
---
　　head 与 tail 就像它的名字一样的浅显易懂，它是用来显示开头或结尾某个数量的文字区块，head 用来显示档案的开头至标准输出中，而 tail 想当然尔就是看档案的结尾。
<!--more -->
#### 命令格式
```bash
head [参数]... [文件]...  
```
#### 命令功能
　　head 用来显示档案的开头至标准输出中，默认head命令打印其相应文件的开头10行。
#### 命令参数
| 参数 | 描述     |
| :------------- | :------------- |
| -q |隐藏文件名 |
| -v | 显示文件名 |
| -c<字节> | 显示字节数 |
| -n<行数> | 显示的行数 |
#### 使用实例
**`例一`：显示文件的前n行**
```bash
$ head -n 5 log2014.log
```
**`例二`：显示文件前n个字节**
```bash
$ head -c 20 log2014.log
```
**`例三`：文件的除了最后n个字节以外的内容**
```bash
$ head -c -32 log2014.log
```
**`例四`：输出文件除了最后n行的全部内容**
```bash
$ head -n -6 log2014.log
```
