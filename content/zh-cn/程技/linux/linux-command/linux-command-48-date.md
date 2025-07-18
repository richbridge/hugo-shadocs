---
title: '每天一个linux命令（48）: date'
date: 2017-01-16 14:39:27
type: posts
cover: https://jsd.cdn.zzko.cn/gh/richbridge/picx-images-hosting@master/thumbnail/程技.jpg
categories: [程技]
tags: ["linux命令"]
---
　　在linux环境中，不管是编程还是其他维护，时间是必不可少的，也经常会用到时间的运算，熟练运用date命令来表示自己想要表示的时间，肯定可以给自己的工作带来诸多方便。
<!--more -->
#### 命令格式
```bash
$ date [参数]... [+格式]
```
#### 命令功能
　　date 可以用来显示或设定系统的日期与时间。
#### 命令参数
**命令参数**

| 参数 | 描述 |
| :- | :- |
| %H | 小时(以00-23来表示) |
| %I | 小时(以01-12来表示) |
| %K | 小时(以0-23来表示) |
| %l | 小时(以0-12来表示) |
| %M | 分钟(以00-59来表示) |
| %P | AM或PM |
| %r | 时间(含时分秒，小时以12小时AM/PM来表示) |
| %s | 总秒数。起算时间为1970-01-01 00:00:00 UTC |
| %S | 秒(以本地的惯用法来表示) |
| %T | 时间(含时分秒，小时以24小时制来表示) |
| %X | 时间(以本地的惯用法来表示) |
| %Z | 市区 |
| %a | 星期的缩写 |
| %A | 星期的完整名称 |
| %b | 月份英文名的缩写 |
| %B | 月份的完整英文名称 |
| %c | 日期与时间。只输入date指令也会显示同样的结果 |
| %d | 日期(以01-31来表示) |
| %D | 日期(含年月日) |
| %j | 该年中的第几天 |
| %m | 月份(以01-12来表示) |
| %U | 该年中的周数 |
| %w | 该周的天数，0代表周日，1代表周一，异词类推 |
| %x | 日期(以本地的惯用法来表示) |
| %y | 年份(以00-99来表示) |
| %Y | 年份(以四位数来表示) |
| %n | 在显示时，插入新的一行 |
| %t | 在显示时，插入tab |
| MM | 月份(必要) |
| DD | 日期(必要) |
| hh | 小时(必要) |
| mm | 分钟(必要) |
| ss | 秒(选择性)  |

**选择参数**

| 参数 | 描述 |
| :- | :- |
| -d<字符串> | 显示字符串所指的日期与时间。字符串前后必须加上双引号 |
| -s<字符串> | 根据字符串来设置日期与时间。字符串前后必须加上双引号 |
| -u | 显示GMT |
| --help | 在线帮助 |
| --version | 显示版本信息 |

#### 使用说明
**1.在显示方面，使用者可以设定欲显示的格式，格式设定为一个加号后接数个标记，其中可用的标记列表如下: % :  打印出 %**
%n : 下一行
%t : 跳格
%H : 小时(00..23)
%I : 小时(01..12)
%k : 小时(0..23)
%l : 小时(1..12)
%M : 分钟(00..59)
%p : 显示本地 AM 或 PM
%r : 直接显示时间 (12 小时制，格式为 hh:mm:ss [AP]M)
%s : 从 1970 年 1 月 1 日 00:00:00 UTC 到目前为止的秒数
%S : 秒(00..61)
%T : 直接显示时间 (24 小时制)
%X : 相当于 %H:%M:%S
%Z : 显示时区 %a : 星期几 (Sun..Sat)
%A : 星期几 (Sunday..Saturday)
%b : 月份 (Jan..Dec)
%B : 月份 (January..December)
%c : 直接显示日期与时间
%d : 日 (01..31)
%D : 直接显示日期 (mm/dd/yy)
%h : 同 %b
%j : 一年中的第几天 (001..366)
%m : 月份 (01..12)
%U : 一年中的第几周 (00..53) (以 Sunday 为一周的第一天的情形)
%w : 一周中的第几天 (0..6)
%W : 一年中的第几周 (00..53) (以 Monday 为一周的第一天的情形)
%x : 直接显示日期 (mm/dd/yy)
%y : 年份的最后两位数字 (00.99)
%Y : 完整年份 (0000..9999)
**2.在设定时间方面**
date -s //设置当前时间，只有root权限才能设置，其他只能查看。
date -s 20080523 //设置成20080523，这样会把具体时间设置成空00:00:00
date -s 01:01:01 //设置具体时间，不会对日期做更改
date -s “01:01:01 2008-05-23″ //这样可以设置全部时间
date -s “01:01:01 20080523″ //这样可以设置全部时间
date -s “2008-05-23 01:01:01″ //这样可以设置全部时间
date -s “20080523 01:01:01″ //这样可以设置全部时间
**3.加减**
date +%Y%m%d         //显示前天年月日
date +%Y%m%d --date="+1 day"  //显示前一天的日期
date +%Y%m%d --date="-1 day"  //显示后一天的日期
date +%Y%m%d --date="-1 month"  //显示上一月的日期
date +%Y%m%d --date="+1 month"  //显示下一月的日期
date +%Y%m%d --date="-1 year"  //显示前一年的日期
date +%Y%m%d --date="+1 year"  //显示下一年的日期
#### 使用实例
**`例一`：显示当前时间**
```bash
$ date
2017年 01月 28日 星期六 14:51:10 CST

$ date '+%c'
2017年01月28日 星期六 14时51分35秒

$ date '+%D'
01/28/17

$ date '+%x'
2017年01月28日

$ date '+%T'
14:52:02

$ date '+%X'
14时52分06秒
```
**`例二`：显示日期和设定时间**
```bash
$ date --date 08:42:00
```
**`例三`：date -d参数使用**
```bash
$ date -d "nov 22"
2012年 11月 22日 星期四 00:00:00 CST

$ date -d '2 weeks'
2012年 12月 22日 星期六 08:50:21 CST

$ date -d 'next monday'
2012年 12月 10日 星期一 00:00:00 CST

$ date -d next-day +%Y%m%d
20121209

$ date -d tomorrow +%Y%m%d
20121209

$ date -d last-day +%Y%m%d
20121207

$ date -d yesterday +%Y%m%d
20121207

$ date -d last-month +%Y%m
201211

$ date -d next-month +%Y%m
201301

$ date -d '30 days ago'
2012年 11月 08日 星期四 08:51:37 CST

$ date -d '-100 days'
2012年 08月 30日 星期四 08:52:03 CST

$ date -d 'dec 14 -2 weeks'
2012年 11月 30日 星期五 00:00:00 CST

$ date -d '50 days'
2013年 01月 27日 星期日 08:52:27 CST
```
>**说明：**
　　date 命令的另一个扩展是 -d 选项，该选项非常有用。使用这个功能强大的选项，通过将日期作为引号括起来的参数提供，您可以快速地查明一个特定的日期。-d 选项还可以告诉您，相对于当前日期若干天的究竟是哪一天，从现在开始的若干天或若干星期以后，或者以前（过去）。通过将这个相对偏移使用引号括起来，作为 -d 选项的参数，就可以完成这项任务。
　　具体说明如下：
　　　　date -d "nov 22"  今年的 11 月 22 日是星期三
　　　　date -d '2 weeks' 2周后的日期
　　　　date -d 'next monday' (下周一的日期)
　　　　date -d next-day +%Y%m%d（明天的日期）或者：date -d tomorrow +%Y%m%d
　　　　date -d last-day +%Y%m%d(昨天的日期) 或者：date -d yesterday +%Y%m%d
　　　　date -d last-month +%Y%m(上个月是几月)
　　　　date -d next-month +%Y%m(下个月是几月)
　　使用 ago 指令，您可以得到过去的日期：
　　　　date -d '30 days ago' （30天前的日期）
　　使用负数以得到相反的日期：
　　　　date -d 'dec 14 -2 weeks' （相对:dec 14这个日期的两周前的日期）
　　　　date -d '-100 days' (100天以前的日期)
　　　　date -d '50 days'(50天后的日期)

**`例四`：显示月份和日数**
```bash
$ date  '+%B %d'
一月 28
```
**`例五`：显示时间后跳行，再显示目前日期**
```bash
$ date '+%T%n%D'
14:58:23
01/28/17
```
