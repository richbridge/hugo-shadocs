---
title: '每天一个linux命令（12）: more'
date: 2016-12-12 21:29:39
type: posts
cover: https://jsd.cdn.zzko.cn/gh/richbridge/picx-images-hosting@master/thumbnail/程技.jpg
categories: [程技]
tags: ["linux命令"]
---
　　more命令，功能类似 cat ，cat命令是整个文件的内容从上到下显示在屏幕上。 more会以一页一页的显示方便使用者逐页阅读，而最基本的指令就是按空白键（space）就往下一页显示，按 b 键就会往回（back）一页显示，而且还有搜寻字串的功能 。more命令从前向后读取文件，因此在启动时就加载整个文件。
<!--more -->
#### 命令格式
```bash
$ more [-dlfpcsu ] [-num ] [+/ pattern] [+ linenum] [file ... ]
```
#### 命令功能
　　more命令和cat的功能一样都是查看文件里的内容，但有所不同的是more可以按页来查看文件的内容，还支持直接跳转行等功能。
#### 命令参数
| 参数 | 描述     |
| :------------- | :------------- |
| +n |从笫n行开始显示 |
|-n|定义屏幕大小为n行|
|+/pattern|每个档案显示前搜寻该字串（pattern），然后从该字串前两行之后开始显示 |
|-c| 从顶部清屏，然后显示|
|-d|提示“Press space to continue，’q’ to quit（按空格键继续，按q键退出）”，禁用响铃功能|
|-l| 忽略Ctrl+l（换页）字符|
|-p|通过清除窗口而不是滚屏来对文件进行换页，与-c选项相似|
|-s|把连续的多个空行显示为一行|
|-u|把文件内容中的下画线去掉|

#### 常用操作
| 操作 | 描述     |
| :------------- | :------------- |
| Enter |向下n行，需要定义。默认为1行 |
|Ctrl+F|向下滚动一屏|
|空格键|向下滚动一屏|
|Ctrl+B|返回上一屏|
|=|输出当前行的行号|
|：f|输出文件名和当前行的行号|
|V|调用vi编辑器|
|!命令|调用Shell，并执行命令 |
|q|退出more|
#### 命令实例
**`例一`：显示文件中从第3行起的内容**
```bash
$ more +3 log2012.log
```
**`例二`：从文件中查找第一个出现"day3"字符串的行，并从该处前两行开始显示输出**
```bash
$ more +/day3 log2012.log
```
**`例三`：设定每屏显示行数**
```bash
$ more -5 log2012.log
```
**`例四`：列一个目录下的文件，由于内容太多，我们应该学会用more来分页显示。这得和管道 | 结合起来**
```bash
$ ls -l  | more -5
```
>**说明：**每页显示5个文件信息，按 Ctrl+F 或者 空格键 将会显示下5条文件信息。
