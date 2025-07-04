---
title: '每天一个linux命令（15）: tail'
date: 2016-12-15 15:00:26
type: posts
cover: https://github.com/richbridge/picx-images-hosting/raw/master/thumbnail/程技.jpg
categories: [程技]
tags: ["linux命令"]
---
　　tail 命令从指定点开始将文件写到标准输出.使用tail命令的-f选项可以方便的查阅正在改变的日志文件,tail -f filename会把filename里最尾部的内容显示在屏幕上,并且不但刷新,使你看到最新的文件内容.
<!--more -->
#### 命令格式
```bash
tail[必要参数][选择参数][文件]
```
#### 命令功能
　　用于显示指定文件末尾内容，不指定文件时，作为输入信息进行处理。常用查看日志文件。
#### 命令参数
| 参数 | 描述     |
| :------------- | :------------- |
| -f |循环读取 |
| -q | 不显示处理信息 |
| -v | 显示详细的处理信息 |
| -c<数目> | 显示的字节数 |
| -n<行数> | 显示行数 |
| --pid=PID | 与-f合用,表示在进程ID,PID死掉之后结束 |
| -q, --quiet, --silent | 从不输出给出文件名的首部 |
| -s, --sleep-interval=S | 与-f合用,表示在每次反复的间隔休眠S秒  |
#### 使用实例
**`例一`：显示文件末尾内容**
```bash
## 显示文件最后5行内容
$ tail -n 5 log2014.log
```
**`例二`：循环查看文件内容**
```bash
$ tail -f test.log
```
**`例三`：从第5行开始显示文件**
```bash
$ tail -n +5 log2014.log
```
