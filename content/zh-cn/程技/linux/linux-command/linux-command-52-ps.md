---
title: '每天一个linux命令（52）: ps'
date: 2017-01-20 09:46:16
type: posts
cover: https://jsd.cdn.zzko.cn/gh/richbridge/picx-images-hosting@master/thumbnail/程技.jpg
categories: [程技]
tags: ["linux命令"]
---
　　Linux中的ps命令是Process Status的缩写。ps命令用来列出系统中当前运行的那些进程。ps命令列出的是当前那些进程的快照，就是执行ps命令的那个时刻的那些进程，如果想要动态的显示进程信息，就可以使用top命令。
<!--more -->
　　要对进程进行监测和控制，首先必须要了解当前进程的情况，也就是需要查看当前进程，而 ps 命令就是最基本同时也是非常强大的进程查看命令。使用该命令可以确定有哪些进程正在运行和运行的状态、进程是否结束、进程有没有僵死、哪些进程占用了过多的资源等等。总之大部分信息都是可以通过执行该命令得到的。
<!--more -->
　　ps 为我们提供了进程的一次性的查看，它所提供的查看结果并不动态连续的；如果想对进程时间监控，应该用 top 工具。

　　kill 命令用于杀死进程。
**linux上进程有5种状态:**
1. 运行(正在运行或在运行队列中等待)
2. 中断(休眠中, 受阻, 在等待某个条件的形成或接受到信号)
3. 不可中断(收到信号不唤醒和不可运行, 进程必须等待直到有中断发生)
4. 僵死(进程已终止, 但进程描述符存在, 直到父进程调用wait4()系统调用后释放)
5. 停止(进程收到SIGSTOP, SIGSTP, SIGTIN, SIGTOU信号后停止运行运行)

**ps工具标识进程的5种状态码:**
D 不可中断 uninterruptible sleep (usually IO)
R 运行 runnable (on run queue)
S 中断 sleeping
T 停止 traced or stopped
Z 僵死 a defunct (”zombie”) process
#### 命令格式
```bash
$ ps [参数]
```
#### 命令功能
用来现实当前进程的状态
#### 命令参数
| 参数 | 描述 |
| :- | :- |
| a | 显示所有进程 |
| -a | 显示同一终端下的所有程序 |
| -A | 显示所有进程 |
| c | 显示进程的真实名称 |
| -N | 反向选择 |
| -e | 等于“-A” |
| e | 显示环境变量 |
| f | 显示程序间的关系 |
| -H | 显示树状结构 |
| r | 显示当前终端的进程 |
| T | 显示当前终端的所有程序 |
| u | 指定用户的所有进程 |
| -au | 显示较详细的资讯 |
| -aux | 显示所有包含其他使用者的行程 |
| -C<命令> | 列出指定命令的状况 |
| --lines<行数> | 每页显示的行数 |
| --width<字符数> | 每页显示的字符数 |
| --help | 显示帮助信息 |
| --version | 显示版本显示 |

#### 使用实例
**`例一`：显示所有进程信息**
```bash
$ ps -A
```
**`例二`：显示指定用户的进程信息**
```bash
$ ps -u faker
```
**`例三`：显示所有进程信息，连同命令行**
```bash
$ ps -ef
```
**`例四`：ps 与grep 常用组合用法，查找特定进程**
```bash
$ ps -ef|grep ssh
```
**`例五`：将目前属于您自己这次登入的 PID 与相关信息列示出来**
```bash
$ ps -l
```
>**说明：**
各相关信息的意义：
　　F 代表这个程序的旗标 (flag)， 4 代表使用者为 super user
　　S 代表这个程序的状态 (STAT)，关于各 STAT 的意义将在内文介绍
　　UID 程序被该 UID 所拥有
　　PID 就是这个程序的 ID ！
　　PPID 则是其上级父程序的ID
　　C CPU 使用的资源百分比
　　PRI 这个是 Priority (优先执行序) 的缩写，详细后面介绍
　　NI 这个是 Nice 值，在下一小节我们会持续介绍
　　ADDR 这个是 kernel function，指出该程序在内存的那个部分。如果是个 running的程序，一般就是 "-"
　　SZ 使用掉的内存大小
　　WCHAN 目前这个程序是否正在运作当中，若为 - 表示正在运作
　　TTY 登入者的终端机位置
　　TIME 使用掉的 CPU 时间。
　　CMD 所下达的指令为何
　　在预设的情况下， ps 仅会列出与目前所在的 bash shell 有关的 PID 而已，所以， 当我使用 ps -l 的时候，只有三个 PID。

**`例六`：列出目前所有的正在内存当中的程序**
```bash
$ ps aux
```
>**说明：**
　　USER：该 process 属于那个使用者账号的
　　PID ：该 process 的号码
　　%CPU：该 process 使用掉的 CPU 资源百分比
　　%MEM：该 process 所占用的物理内存百分比
　　VSZ ：该 process 使用掉的虚拟内存量 (Kbytes)
　　RSS ：该 process 占用的固定的内存量 (Kbytes)
　　TTY ：该 process 是在那个终端机上面运作，若与终端机无关，则显示 ?，另外， tty1-tty6 是本机上面的登入者程序，若为 pts/0 等等的，则表示为由网络连接进主机的程序。
　　STAT：该程序目前的状态，主要的状态有
　　R ：该程序目前正在运作，或者是可被运作
　　S ：该程序目前正在睡眠当中 (可说是 idle 状态)，但可被某些讯号 (signal) 唤醒。
　　T ：该程序目前正在侦测或者是停止了
　　Z ：该程序应该已经终止，但是其父程序却无法正常的终止他，造成 zombie (疆尸) 程序的状态
　　START：该 process 被触发启动的时间
　　TIME ：该 process 实际使用 CPU 运作的时间
　　COMMAND：该程序的实际指令

**`例七`：列出类似程序树的程序显示**
```bash
$ ps -axjf
```
**`例八`：找出与 cron 与 syslog 这两个服务有关的 PID 号码**
```bash
$ ps aux | egrep '(cron|syslog)'
```
**`其他`**
```bash
## 可以用 | 管道和 more 连接起来分页查看
$ ps -aux |more

## 把所有进程显示出来，并输出到ps001.txt文件
$ ps -aux > ps001.txt

## 输出指定的字段
$ ps -o pid,ppid,pgrp,session,tpgid,comm
```
