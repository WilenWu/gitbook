---
title: 大数据手册(Linux)--Linux基础知识
tags: [linux,大数据]
mathjax: false
copyright: true
date: 2018-06-17 19:26:49
categories: [Big Data]
sticky: false
---

------

[大数据手册(Linux)--Linux基础知识](https://wilenwu.github.io/big-data/BigDataNotebook(Linux)--Linux-base.html.html)
[大数据手册(Linux)--Linux Shell 教程](https://wilenwu.github.io/big-data/BigDataNotebook(Linux)--Linux-shell.html)

------

# Linux简介

Linux是一套免费使用和自由传播的类Unix操作系统，是一个基于POSIX和UNIX的多用户、多任务、支持多线程和多CPU的操作系统。它能运行主要的UNIX工具软件、应用程序和网络协议。它支持32位和64位硬件。Linux继承了Unix以网络为核心的设计思想，是一个性能稳定的多用户网络操作系统。
<!-- more -->
目前市面上较知名的发行版有：Ubuntu、RedHat、CentOS、Debian、Fedora、SuSE、OpenSUSE、Arch Linux、SolusOS 等。

今天各种场合都有使用各种Linux发行版，从嵌入式设备到超级计算机，并且在服务器领域确定了地位，通常服务器使用LAMP（Linux + Apache + MySQL + PHP）或LNMP（Linux + Nginx+ MySQL + PHP）组合。

> Ubuntu18内置GNOME ，发音/noʊm/
即GNU网络对象模型环境 (The GNU Network Object Model Environment)计划的一部分，开放源码运动的一个重要组成部分。是一种让使用者容易操作和设定电脑环境的工具。


## Linux 关机

关机|说明
---|---
sync|将数据由内存同步到硬盘中
init 0|关闭系统
Shutdown –h now |立马关机
Shutdown –h 20:25 |系统会在今天20:25关机
Shutdown –h +10 |十分钟后关机
**重启**|
init 6|重启系统
Shutdown –r now |系统立马重启
Shutdown –r +10 |系统十分钟后重启
reboot |就是重启，等同于 shutdown –r now
**注销**|
logout|注销


## 远程登陆

- SSH 为安全外壳协议 (Secure Shell) 的缩写，建立在应用层基础上的安全协议。
- SSH 是目前较可靠，专为远程登录会话和其他网络服务提供安全性的协议。
- SSH客户端适用于多种平台。几乎所有UNIX平台—包括HP-UX、Linux、AIX、Solaris、Digital UNIX、Irix，以及其他平台，都可运行SSH。

服务器上安装ssh终端，在mac、Linux上通过ssh命令即可访问，windows上用power shell或安装内置Ubuntu子系统，或安装putty、Xshell、SecureCRT等软件也可访问。
> Tips
> SecureCRT修改默认配置文件（默认模式，编码格式等）：
> 安装目录/config/session/default.ini
```shell
sudo apt-get install openssh-server #安装ssh服务终端

ssh username@192.168.0.1  #linux、mac、powershell通过用户名和IP访问
exit   #注销登陆

#-----------免密码登陆-----------
#在控制端建立public key，共享到服务器
ssh-keygen  #在Mac终端或Windows PowerShell 生成key
ssh-copy-id username@192.168.0.1   #共享到服务器端
ssh username@192.168.0.1  #免密登陆

#------------上传下载文件---------
scp file username@192.168.0.1:~/Document/  #上传
scp username@192.168.0.1:~/Document/ ~/file  #下载
```

## Linux上传和下载命令用法

rz，sz是Linux/Unix同Windows进行ZModem文件传输的命令行工具。

sz（Send Zmodem）：将选定的文件发送（send）到本地机器
rz（Receive Zmodem）：运行该命令会弹出一个文件选择窗口，从本地选择文件上传到Linux服务器
```shell
yum install lrzsz  #安装工具
sz filename   #从服务端发送文件到客户端
rz            #从客户端上传文件到服务端，在弹出的框中选择文件
```
SecureCRT设置默认路径：Options -> Session Options -> Terminal -> Xmodem/Zmodem ->Directories
Xshell设置默认路径：右键会话 -> 属性 -> ZMODEM -> 接收文件夹

# Linux 重要系统目录

- **/home**：用户的主目录
-  **/root**：该目录为系统管理员，也称作超级权限者的用户主目录。
- **/bin**：bin是Binary的缩写, 常用的可执行文件
- **/sbin**：s就是Super User的意思，这里存放的是系统管理员使用的系统管理程序。
- **/boot**：启动Linux时使用的一些核心文件
- **/dev** ：Device(设备), 该目录下存放的是Linux的外部设备
- **/etc**：系统管理所需要的配置文件和子目录。
- **/lib**：这个目录里存放着系统最基本的动态连接共享库，其作用类似于Windows里的DLL文件。几乎所有的应用程序都需要用到这些共享库。
- **/lost+found**：这个目录一般情况下是空的，当系统非法关机后，这里就存放了一些文件。
- **/proc**：这个目录是一个虚拟的目录，它是系统内存的映射，我们可以通过直接访问这个目录来获取系统信息。
- **/tmp**：这个目录是用来存放一些临时文件的。
- **/usr**： 这是一个非常重要的目录，用户的很多应用程序和文件都放在这个目录下，类似于windows下的program files目录。

# Linux 文件与目录管理

## 文件和目录

- `/` 最顶级的根目录
- `~` home目录
- `..` 上层目录
- `../..`上两级目录
- `.` 当前目录
- 隐藏目录或者文件名以 `.` 开始
- 绝对路径必须以`/`开头，相对路径则较短
- `--help`参数或前面加`man`，获取帮助文档

## 文件和目录常用操作命令

ls|列出目录
---|---
ls -a |显示隐藏文件
ls -l|显示详细内容
ls -d|显示目录本身的属性
**cd**|**切换目录(Change Directory)**
cd dir|dir 为相对路径或绝对路径
**pwd**| **显示当前目录**(Print Working Directory)
pwd -P|显示出确实的路径，而非使用连结 (link) 路径

创建目录或文件|说明
---|---
mkdir [-mp] dir|创建新目录
touch [options] files|创建文件
**复制文件或目录**|
cp [options] source1 source2 source3 .... directory|
参数：<br>-f<br>-i<br>-r|<br>强制复制，若已存在目录则覆盖<br>交互复制<br>递归复制目录
**移除文件或目录**|
rm [options] file_or_dir| 移除文件或目录
参数：<br>-f<br>-i<br>-r|<br>强制删除<br>交互删除<br>递归删除目录
rmdir [-p] dir|删除一个空的目录
**移动文件与目录，或重命名**|
mv [options] source1 source2 source3 .... directory|
参数：<br>-f<br>-i<br>-u|<br>强制移动<br>交互移动<br>升级(update)

文件内容查看|说明
---|---
cat [options] file|由第一行开始显示文件内容
tac [options] file |从最后一行开始显示
参数：<br>-b<br>-n|<br>列出行号，包括空白行<br>列出行号，不包括空白行
nl [options] file  |显示行号输出
more file|分页显示
less file|分页显示
head [-n number]|显示前number行
tail [-n number]|显示后number行

## Linux文件权限

Linux使用user和group控制使用者对文件的权限，每个文件或程序都有ower和group
![file](/images/Linux_file.png)

`ls -l` 显示文件详细信息
`chmod [options]  mode file` 修改文件权限
> mode参数 : 权限设定字串，`[ugoa...][+-=][rwxX]`
> 
> u 表示用户，g 表示群组，o 其他人，a 表示全部
> `+` 表示增加权限，`-` 表示取消权限，`=` 表示唯一设定权限。
> r(read)只读，w(write)写入，x(execute)  可执行

## 文件的压缩和打包

Linux支持的压缩格式

- Z：compress程序压缩文件
- gz：gzip程序压缩文件
- bz2：bzip2程序压缩文件
- tar：tar程序打包文件，并未压缩
- tar.gz：tar程序打包文件，gzip程序压缩文件
- tar.bz2：tar程序打包文件，bzip2程序压缩文件

`gzip [-cdtv#] file`
> 参数：
> -c：压缩的数据输出到屏幕
> -d：解压缩的参数
> -t：进行文件一致性校验，看是否损坏
> -v：显示和源文件对比的压缩比
> -#：压缩等级，-1最快，-9最慢，默认-6

`bzip2 [-cdkzv#] file`
> 参数：
> -k：保留源文件
> -z：压缩的参数，该参数代表时执行压缩操作
> 其他参数同gzip

```
tar [-jcvf]  filename.tar.bz2 dir #bz2程序打包并压缩
tar [-jxvf]  filename.tar.bz2 -C dir #bz2程序解压缩
```
> 参数：
> -c：建立打包档案
> -t：查看打包文件的文件名
> -x：解压缩或解打包文件，和-C配合
> -j：通过bz2程序操作
> -z：通过gzip程序操作
> -v：将正在处理的文件名显示出来
> dir：要压缩或解压的目录

## 文件编辑

[参考链接 Linux vi/vim](http://www.runoob.com/linux/linux-vim.html)

# 用户和群组

命令|说明
:---|:---
useradd [options] username|添加用户<br>{-d:用户主目录,-m:创建主目录,-g:用户组,-G:附加组,-s:用户的登录Shell,-u:用户号}|
userdel [-r] username|删除用户，-r连同主目录一起删除|
usermod [options] username|修改用户，选项同`useradd`|
passwd [options] username|口令管理<br>-l:锁定口令，即禁用账号,-u:口令解锁,-d:使账号无口令,-f:强迫用户下次登录时修改口令|
groupadd [-go] groupname|添加用户组|
groupdel  groupname|删除用户组|
groupmod [-gon] groupname|修改用户组|

# Shell基础

Shell 是指一种应用程序，这个应用程序提供了一个界面，用户通过这个界面访问操作系统内核的服务。Linux 的 Shell 种类众多，常见的有：

Bourne Shell（/usr/bin/sh或/bin/sh）
Bourne Again Shell（/bin/bash）
C Shell（/usr/bin/csh）
K Shell（/usr/bin/ksh）
Shell for Root（/sbin/sh）
... ...

## 运行 Shell 脚本
**作为可执行程序**
```shell
chmod +x test.sh  #使脚本具有执行权限
./test.sh  #在子shell中执行脚本
```
**作为解释器参数（子shell中执行）**
```shell
sh test.sh
php test.php
```

**加载shell脚本（在本shell中加载执行）**
```bash
source test.sh   #脚本中的变量可被引用
```

## Shell 输入/输出重定向

- 标准输入(stdin)，代码0 
- 标准输出(stdout)是指令成功时返回的结果，代码是1
- 标准错误输出(stderr)是指令执行失败返回的错误信息，代码是2

命令	|说明
---|---
command > file	|把 stdout 重定向到 file 文件中
command >> file	|stdout 重定向到 file 文件中(追加)
command 2> file |把 stderr 重定向到 file 文件中；
command 2>> file |把 stderr 重定向到 file 文件中(追加)；
command < file	|command 命令以 file 文件作为 stdin
command > file 2>&1 |把 stdout 和 stderr 一起重定向到 file 文件中；
command >> file 2>&1 |把 stdout 和 stderr 一起重定向到 file 文件中(追加)；
command1 < infile > outfile |command 命令以 infile 文件作为 stdin，以 outfile 文件作为 stdout；
cat <>file |以读写的方式打开 file
`>&n` |使用系统调用 dup2复制文件描述符 n 并把结果用作标准输出
`<&n` |标准输入复制自文件描述符 n
`<&-` |关闭标准输入（键盘）
`>&-` |关闭标准输出
`n<&-` |表示将 n 号输入关闭
`n>&-` |表示将 n 号输出关闭
```bash
cat 'hello' > file.txt
cat < file.txt
```


## 管道操作

Linux管道符`|`处理经由前面一个指令传出的正确输出信息（对错误信息信息没有直接处理能力）传递给下一个命令，作为标准的输入。
```shell
last_part=`hive -e "show partitions employee;" | tail -1`
```

# Ubuntu包管理工具

## dpkg
dpkg(Debian Package Management System) 是ubuntu/Debian下的二进制包(.deb格式)管理系统，包括安装、删除、查询等。
dpkg常用命令|说明
---|---
dpkg -i pkgname.deb|安装软件
dpkg -r pkgname|删除软件
dpkg --info pkgname.deb|查询软件包信息
dpkg --status pkgname|
dpkg --listfiles pkgname|查询软件包所含文件
dpkg --contents pkgname.deb|
dpkg --seach filename|查询文件归属
dpkg -l|查询系统中的包

## apt

apt(Advanced Packaging Tool)是ubuntu/debian及派生发行版的软件包管理工具，可以自动下载，配置，安装二进制或者源代码格式的软件包。

apt常用命令|说明
---|---
apt-get install pkg|安装软件
apt-get remove pkg|删除软件
apt-cache show pkg|查询包信息
apt-file list pkg|查询软件包所含文件
apt-file search filename|查询文件归属
apt-cache pkg|查询系统中的包

## 添加或删除软件源
[给ubuntu16.04更新软件源](https://blog.csdn.net/u012481692/article/details/78740406)
[在Ubuntu中添加和删除PPA的软件源](在Ubuntu中添加和删除PPA的软件源)

## 安装常用软件
```bash
#mysql
sudo apt-get install mysql-client
sudo apt-get install mysql-server
```


# Linux常用操作

## 常用命令

常用命令|说明|示例
--|--|--
echo string|输出字符串|`echo "It is a test"`
locate filename|查找子目录和文件
sudo command|以系统管理者的身份执行指令
date +format|显示当前完整的时间<br>转换格式<br>日期加减运算|`date '+%D' `<br>`date -d '2018-08-05' '+%Y%m'`<br>`date -d '+2 months 2018-08-05'`
ifconfig|查看局域网IP|
curl ifconfig.me|查看外网IP|
scp file1 file2|上传或下载文件
exit n|退出当前脚本，参数n为默认约定，0表示成功，非0表示失败
grep patern files|在file中查找pattern|
printf  format-string  [arguments...]|指定格式输出|`printf "%-10s %-8s %-4s\n" 姓名 性别 体重kg`
jobs -l |显示任务详情
kill -9 id|结束任务id
nohup command > log 2>&1 &|[linux后台执行命令](https://blog.csdn.net/liuyanfeier/article/details/62422742)，必须转化为Linux格式运行

```shell
today=`date +"%Y%m%d"`
last_date=``date -d "-1 day ${today:0:6}01" +"%Y%m%d"
sed -i "1d" filename #删除第一行
```

## 定期执行程序

linux任务调度的工作主要分为以下两类：

**系统执行的工作**：系统周期性所要执行的工作，如备份系统数据、清理缓存
**个人执行的工作**：某个用户定期要做的工作，例如每隔10分钟检查邮件服务器是否有新信，这些工作可由每个用户自行设置

```shell
crontab [ -u user ] file
```
> 参数说明：
file：时程表文件
-e : 执行文字编辑器来设定时程表（默认vi）
-r : 删除目前的时程表
-l : 列出目前的时程表

**时程表文件格式：**

```shell
minute hour day month dayofweek command
```
组件|说明
:--|---
minute |0-60
hour|0-23
day |1-31
month |1-12
dayofweek|0-6
command|要执行的程序
\*|代表任意时间
\*/n|代表每隔n时间
a-b|代表a到b这段区间
a, b, c,...|分别在a, b, c,... 时间执行

**example**
```shell
0 * * * * /bin/ls              #每小时的0分钟执行ls
0 6-12/3 * 12 * cd /usr/bin/ && sh backup > log 2>&1 & #12月每天6-12点每隔3小时执行一次backup
```

## Spark集群配置免密钥登陆

```bash
#在每个节点生成公钥文件
cd ~/.ssh                      #进到当前用户的隐藏目录
ssh-keygen -t rsa              #用rsa生成密钥，一路回车
cp id_rsa.pub authorized_keys   #把公钥复制一份，并改名为authorized_keys
#这步执行完后，在当前机器执行ssh localhost可以无密码登录本机了

#每个节点的公钥文件复制到master节点
scp authorized_keys master@master：~/download/note01_keys   #重命名公钥便于整合
scp authorized_keys master@master：~/download/note01_keys
... ...

 #进入master节点，整合公钥文件分发到所有节点覆盖
cat ~/download/note01_keys >> ~/.ssh/authorized_keys
cat ~/download/note02_keys >> ~/.ssh/authorized_keys
... ...
scp ~/.ssh/authorized_keys node01@node01：~/.ssh/authorized_keys
scp ~/.ssh/authorized_keys node02@node02：~/.ssh/authorized_keys
... ...

#在每个节点更改公钥的权限
chmod 600 authorized_keys
```

## Linux系统自定义shell命令（以pycharm为例）

```bash
#打开配置文件
sudo vim ~/.bashrc   
#添加pycharm.sh所在的路径
alias pycharm = "bash /download/pycharm-community-2018.1.4/bin/pycharm.sh"
#重新加载
source ~/.bashrc 
#运行
pycharm
```

## shell中的参数传入R或Python脚本

[shell中调用R语言并传入参数的两种方法](https://blog.csdn.net/crystal_tyan/article/details/42214339)
[Python中 sys.argv的用法简明解释](https://www.cnblogs.com/aland-1415/p/6613449.html)

## [Ubuntu下JDK和openJDK](https://blog.csdn.net/z5234032/article/details/62886879)

## [ubuntu/linux桌面添加快捷方式](https://jingyan.baidu.com/article/5553fa82c641ba65a23934a5.html)

# 错误处理

- **安装R包报错处理**
安装R包报错时，通常都会显示错误信息，只要按提示的错误信息安装对应的软件包即可。
`sudo apt-get install libxml2-dev`
![](/images/Linux_error.png)

- **pycharm**
打开脚本报错Gtk-Message: Failed to load module "canberra-gtk-module"
解决方法：`sudo apt-get install libcanberra-gtk-module  `



参考链接：

[Linux入门教程链接](www.runoob.com/linux/linux-system-contents.html)
[Linux 简易教学 (机器学习/深度学习 莫烦 Python 教程)-bilibili](https://www.bilibili.com/video/av15976434)
[RHadoop培训 之 Linux基础课](http://blog.fens.me/rhadoop-linux-basic/)
[在win10系统下安装ubuntu17.10以及基本配置](https://blog.csdn.net/strugglm/article/details/78608940?locationNum=9&fps=1)



