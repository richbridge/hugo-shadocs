---
title: '每天一个linux命令（23）: 用SecureCRT来上传和下载文件'
date: 2016-12-23 09:48:15
type: posts
cover: https://github.com/richbridge/picx-images-hosting/raw/master/thumbnail/程技.jpg
categories: [程技]
tags: ["linux命令"]
---
　　用SSH管理linux服务器时经常需要远程与本地之间交互文件.而直接用SecureCRT自带的上传下载功能无疑是最方便的，SecureCRT下的文件传输协议有ASCII、Xmodem、Zmodem。
<!--more -->
**文件传输协议**
　　文件传输是数据交换的主要形式。在进行文件传输时，为使文件能被正确识别和传送，我们需要在两台计算机之间建立统一的传输协议。这个协议包括了文件的识别、传送的起止时间、错误的判断与纠正等内容。常见的传输协议有以下几种：
1. ASCII：这是最快的传输协议，单只能传输文本文件。
2. Xmodem：这种古老的传输协议速度较慢，但由于使用了CRC错误侦测方法，传输的准确率可高达99.6%。
3. Ymodem：这是Xmodem的改良版，使用了1024位区段传送，速度比Xmodem要快
4. Zmodem：Zmodem采用了串流式（streaming）传输方式，传输速度较快，而且还具有自动改变区段大小和断点续传、快速错误侦测等功能。这是目前最流行的文件传输协议。

　　除以上几种外，还有Imodem、Jmodem、Bimodem、Kermit、Lynx等协议，由于没有多数厂商支持，这里就略去不讲。

　　SecureCRT可以使用linux下的zmodem协议来快速的传送文件,使用非常方便.具体步骤：
#### 在使用SecureCRT上传下载之前需要给服务器安装lrzsz
- 从下面的地址下载 lrzsz-0.12.20.tar.gz

[我是下载地址](http://down1.chinaunix.net/distfiles/lrzsz-0.12.20.tar.gz)
- 查看里面的INSTALL文档了解安装参数说明和细节
- 解压文件

```bash
$ tar zxvf lrzsz-0.12.20.tar.gz
```
- 进入目录，配置编译

```bash
$ cd lrzsz-0.12.20
$ ./configure --prefix=/usr/local/lrzsz
$ make
$ make install
```
- 建立软链接

```bash
$ cd /usr/bin
$ ln -s /usr/local/lrzsz/bin/lrz rz
$ ln -s /usr/local/lrzsz/bin/lsz sz
```
- 测试

　　运行 rz 弹出 SecureCrt上传窗口，用SecureCRT来上传和下载文件。
#### 设置SecureCRT上传和下载的默认目录
　　options->session options ->Terminal->Xmodem/Zmodem
　　右栏directory设置上传和下载的目录
#### 使用Zmodem从客户端上传文件到linux服务器
　　用SecureCRT登陆linux终端

　　选中你要放置上传文件的路径，在目录下然后输入rz命令,SecureCRT会弹出文件选择对话框，在查找范围中找到你要上传的文件，按Add按钮。然后OK就可以把文件上传到linux上了。

　　或者在Transfer->Zmodem Upoad list弹出文件选择对话框，选好文件后按Add按钮。然后OK窗口自动关闭。然后在linux下选中存放文件的目录，输入rz命令。liunx就把那个文件上传到这个目录下了。
#### 使用Zmodem下载文件到客户端
```bash
$ sz filename
```
　　zmodem 接收可以自行启动.下载的文件存放在你设定的默认下载目录下

>`rz`，`sz` 是 Linux/Unix 同 Windows 进行 ZModem 文件传输的命令行工具 , windows 端需要支持ZModem的telnet/ssh客户端，SecureCRT 就可以用 SecureCRT 登陆到 Unix/Linux 主机（telnet或ssh均可）O 运行命令rz，即是接收文件，SecureCRT就会弹出文件选择对话框，选好文件之后关闭对话框，文件就会上传到当前目录 O 运行命令sz file1 file2就是发文件到windows上（保存的目录是可以配置） 比ftp命令方便多了，而且服务器不用再开FTP服务了
