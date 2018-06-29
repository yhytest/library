## 1.Linux常用操作命令
4.快捷键：
ctrl + c：停止进程

ctrl + l：清屏

ctrl + r：搜索历史命令

ctrl + q：退出

5.善于用tab键

pwd 显示当前的路径
cd 改变当前路径，无参数时进入对应用户的home目录
ls 列出当前目录下的文件。此命令有N多参数，比如ls -al
ps 列出当前系统进程
kill 杀死某个进程
mkdir 建立目录
rmdir 删除目录
rm 删除文件
mv 文件改名或目录改名
man 联机帮助
tail 显示文件的最末几行

## 2.Linux文件操作
pwd 显示当前工作目录（print working directory）
touch 创建空文件				                    
mkdir 创建目录（make directoriy）
-p 父目录不存在情况下先生成父目录 （parents）            
cp 复制文件或目录（copy）
-r 递归处理，将指定目录下的文件与子目录一并拷贝（recursive）     
mv 移动文件或目录、文件或目录改名（move）

**软连接（快捷方式）**

* 创建软链接

    ln –s  /var/www/test  test 当前路径创建test 引向/var/www/test 文件夹 

* 修改软链接指向的路径

    ln –snf  /var/www/test1   test 

* 删除软链接test

    rm –rf test 
## 3.用户管理
**用户名**

* 创建用户名    useradd 用户名 * 修改用户名 usermod -l 新名 原名* 删除用户名	userdel 用户名

**用户组**

* 创建用户组     `groupadd 组名` * 修改用户组groupmod -n 新名 原名* 删除用户组groupdel 用户组

**密码**

* 设置密码 	`passwd 密码`
	

**切换用户** * 切换用户   `su - 用户名` 

## 3.Linux权限操作
三种基本权限 r 可读（read） w 可写（write）x 可执行 （execute）

## 4.网络与工具
netstat 显示网络状态信息
ifconfig 网卡网络配置详解 
ping 测试网络的连通性 
wc 统计文本的行数、字数、字符数（word count）
find 在文件系统中查找指定的文件
find /etc/ -name "aaa"
grep 在指定的文本文件中查找指定的字符串
ln 建立链接文件（link）
-s 对源文件建立符号连接，而非硬连接（symbolic）

rm 删除文件（remove）
-r 同时删除该目录下的所有文件（recursive）
-f 强制删除文件或目录（force）
rmdir 删除空目录（remove directoriy）
cat显示文本文件内容 （catenate）
more、less 分页显示文本文件内容
head、tail查看文本中开头或结尾部分的内容
haed  -n  5  a.log 查看a.log文件的前5行
tail  -F b.log 循环读取（follow）

shutdown系统关机 
reboot 重新启动

## 5.打包压缩与定时作业

## 6.查找 
## 软件安装
**rpm安装，升级，卸载**
* rpm -ivh 软件包 软件安装 rpm -Uvh 软件包 软件安装
* rpm -qa |grep jdk   查询当前安装的jdk   rpm -e jdk 卸载jdk

**yum安装，升级，卸载**
* yum  install  gcc-c++ yum  update  gcc-c++ yum  remove  gcc-c++ 
##7.打包

## 8.进程控制
1.查看用户最近登录情况
last
lastlog

2.查看硬盘使用情况
df

3.查看文件大小
du

4.查看内存使用情况
free

5.查看文件系统
/proc

6.查看日志
ls /var/log/

7.查看系统报错日志
tail /var/log/messages

8.查看进程
top

9.结束进程
kill 1234
kill -9 4333

## 输入输出重定向以及管道
1.新建一个文件
touch a.txt
> b.txt

2.错误重定向:2>
find /etc -name zhaoxing.txt 2> error.txt

3.将正确或错误的信息都输入到log.txt中
find /etc -name passwd > /tmp/log.txt 2>&1 
find /etc -name passwd &> /tmp/log.txt

4.追加>>

5.将小写转为大写（输入重定向）
tr "a-z" "A-Z" < /etc/passwd

6.自动创建文件
cat > log.txt << EXIT
> ccc
> ddd
> EXI

7.查看/etc下的文件有多少个？
ls -l /etc/ | grep '^d' | wc -l

8.查看/etc下的文件有多少个，并将文件详情输入到result.txt中
ls -l /etc/ | grep '^d' | tee result.txt | wc -l

## 打包与压缩

1.gzip压缩
gzip a.txt

2.解压
gunzip a.txt.gz
gzip -d a.txt.gz

3.bzip2压缩
bzip2 a

4.解压
bunzip2 a.bz2
bzip2 -d a.bz2

5.将当前目录的文件打包
tar -cvf bak.tar .
将/etc/password追加文件到bak.tar中(r)
tar -rvf bak.tar /etc/password

6.解压
tar -xvf bak.tar

7.打包并压缩gzip
tar -zcvf a.tar.gz

8.解压缩
tar -zxvf a.tar.gz
解压到/usr/下
tar -zxvf a.tar.gz -C /usr

9.查看压缩包内容
tar -ztvf a.tar.gz

zip/unzip

10.打包并压缩成bz2
tar -jcvf a.tar.bz2

11.解压bz2
tar -jxvf a.tar.bz2

## 查找

1.查找可执行的命令：
which ls

2.查找可执行的命令和帮助的位置：
whereis ls

3.查找文件(需要更新库:updatedb)
locate hadoop.txt

4.从某个文件夹开始查找
find / -name "hadooop*"
find / -name "hadooop*" -ls

5.查找并删除
find / -name "hadooop*" -ok rm {} \;
find / -name "hadooop*" -exec rm {} \;

6.查找用户为hadoop的文件
find /usr -user hadoop -ls

7.查找用户为hadoop并且(-a)拥有组为root的文件
find /usr -user hadoop -a -group root -ls

8.查找用户为hadoop或者(-o)拥有组为root并且是文件夹类型的文件
find /usr -user hadoop -o -group root -a -type d

9.查找权限为777的文件
find / -perm -777 -type d -ls

10.显示命令历史
history

11.grep
grep hadoop /etc/password

## 软件安装

1.安装JDK
	*添加执行权限 
		chmod u+x jdk-6u45-linux-i586.bin
	*解压
		./jdk-6u45-linux-i586.bin
	*在/usr目录下创建java目录
		mkdir /usr/java
	*将/soft目录下的解压的jdk1.6.0_45剪切到/usr/java目录下
		mv jdk1.6.0_45/ /usr/java/
	*添加环境变量
		vim /etc/profile
		*在/etc/profile文件最后添加
			export JAVA_HOME=/usr/java/jdk1.6.0_45
			export CLASSPATH=$JAVA_HOME/lib
			export PATH=$PATH:$JAVA_HOME/bin
	*更新配置
		source /etc/profile
		
2.安装tomcat
	tar -zxvf /soft/apache-tomcat-7.0.47.tar.gz -C /programs/
	cd /programs/apache-tomcat-7.0.47/bin/
	./startup.sh
	
3.安装eclipse
	
## vim 编辑器
i
a/A
o/O
r + ?替换

0:文件当前行的开头
$:文件当前行的末尾
G:文件的最后一行开头
1 + G到第一行 
9 + G到第九行 = :9

dd:删除一行
3dd：删除3行
yy:复制一行
3yy:复制3行
p:粘贴
u:undo
ctrl + r:redo

"a剪切板a
"b剪切板b

"ap粘贴剪切板a的内容

每次进入vi就有行号
vi ~/.vimrc
set nu

:w a.txt另存为
:w >> a.txt内容追加到a.txt

:e!恢复到最初状态

:1,$s/hadoop/root/g 将第一行到追后一行的hadoop替换为root
:1,$s/hadoop/root/c 将第一行到追后一行的hadoop替换为root(有提示)

## 权限

创建a.txt和b.txt文件，将他们设为其拥有者和所在组可写入，但其他以外的人则不可写入:
chmod ug+w,o-w a.txt b.txt

创建c.txt文件所有人都可以写和执行
chmod a=wx c.txt 或chmod 666 c.txt

将/itcast目录下的所有文件与子目录皆设为任何人可读取
chmod -R a+r /itcast

将/itcast目录下的所有文件与子目录的拥有者设为root，用户拥有组为users
chown -R root:users /itcast

将当前目录下的所有文件与子目录的用户皆设为itcast，组设为users
chown -R itcast:users *

## 系统命令

1.查看主机名
hostname

2.重启所有网卡
service network restart 

3.修改主机名(重启后永久生效)
vi /ect/sysconfig/network

5.修改IP(重启后永久生效)
vi /etc/sysconfig/network-scripts/ifcfg-eth0

6.查看系统信息
uname 

8.日期
date

9.日历
cal 2012

10.查看文件信息
file filename


12.查看文件大小
du -h

13.查看分区
df -h

14.ssh
ssh hadoop@192.168.1.1

15.关机
shutdown 

16.重启
reboot

查看进程
ps -aux //查看所有进程（静态）

top //查看动态变化的进程

jobs //查看后台运行的进程

kill -9 PID 
killall -9 进程名  强制结束进程

## 文件有关

1.进入到用户根目录
cd ~ 或者 cd
cd ~hadoop
回到原来路径
cd -

2.查看文件详情
stat a.txt

3.移动
mv a.txt /ect/
改名
mv b.txt a.txt
移动并改名
mv a.txt ../b.txt

4拷贝并改名
cp a.txt /etc/b.txt

5.vi撤销修改
ctrl + u (undo)
恢复
ctrl + r (redo)

6.名令设置别名(重启后无效)
alias ll="ls -l"
取消
unalias ll

7.如果想让别名重启后仍然有效需要修改
vi ~/.bashrc

8.添加用户
useradd hadoop
passwd hadoop

9创建多个文件
touch a.txt b.txt
touch /home/{a.txt,b.txt}

10.将一个文件的内容复制到里另一个文件中
cat a.txt > b.txt
追加内容
cat a.txt >> b.txt 


11.将a.txt 与b.txt设为其拥有者和其所属同一个组者可写入，但其他以外的人则不可写入:
chmod ug+w,o-w a.txt b.txt

chmod a=wx c.txt

12.将当前目录下的所有文件与子目录皆设为任何人可读取:
chmod -R a+r *

13.将a.txt的用户拥有者设为users,组的拥有者设为jessie:
chown users:jessie a.txt

14.将当前目录下的所有文件与子目录的用户的使用者为lamport,组拥有者皆设为users，
chown -R lamport:users *

15.将所有的java语言程式拷贝至finished子目录中:
cp *.java finished

16.将目前目录及其子目录下所有扩展名是java的文件列出来。
find -name "*.java"
查找当前目录下扩展名是java 的文件
find -name *.java

17.删除当前目录下扩展名是java的文件
rm -f *.java

## 常用命令

说明：安装linux时，创建一个itcast用户，然后使用root用户登陆系统

1.进入到用户根目录
cd ~ 或 cd

2.查看当前所在目录
pwd

3.进入到itcast用户根目录
cd ~itcast

4.返回到原来目录
cd -

5.返回到上一级目录
cd ..

6.查看itcast用户根目录下的所有文件
ls -la

7.在根目录下创建一个itcast的文件夹
mkdir /itcast

8.在/itcast目录下创建src和WebRoot两个文件夹
分别创建：mkdir /itcast/src
		  mkdir /itcast/WebRoot
同时创建：mkdir /itcast/{src,WebRoot}

进入到/itcast目录，在该目录下创建.classpath和README文件
分别创建：touch .classpath
		  touch README
同时创建：touch {.classpath,README}

查看/itcast目录下面的所有文件
ls -la

在/itcast目录下面创建一个test.txt文件,同时写入内容"this is test"
echo "this is test" > test.txt

查看一下test.txt的内容
cat test.txt
more test.txt
less test.txt

向README文件追加写入"please read me first"
echo "please read me first" >> README

将test.txt的内容追加到README文件中
cat test.txt >> README

拷贝/itcast目录下的所有文件到/itcast-bak
cp -r /itcast /itcast-bak

进入到/itcast-bak目录，将test.txt移动到src目录下，并修改文件名为Student.java
mv test.txt src/Student.java

在src目录下创建一个struts.xml
> struts.xml

删除所有的xml类型的文件
rm -rf *.xml

删除/itcast-bak目录和下面的所有文件
rm -rf /itcast-bak

返回到/itcast目录，查看一下README文件有多单词，多少个少行
wc -w README
wc -l README

返回到根目录，将/itcast目录先打包，再用gzip压缩
分步完成：tar -cvf itcast.tar itcast
		  gzip itcast.tar
一步完成：tar -zcvf itcast.tar.gz itcast
		  
将其解压缩，再取消打包
分步完成：gzip -d itcast.tar.gz 或 gunzip itcast.tar.gz
一步完成：tar -zxvf itcast.tar.gz

将/itcast目录先打包，同时用bzip2压缩，并保存到/tmp目录下
tar -jcvf /tmp/itcast.tar.bz2 itcast

将/tmp/itcast.tar.bz2解压到/usr目录下面
tar -jxvf itcast.tar.bz2 -C /usr/

## 

1.内部命令：echo
查看内部命令帮助：help echo 或者 man echo

2.外部命令：ls
查看外部命令帮助：ls --help 或者 man ls 或者 info ls

3.man文档的类型(1~9)
man 7 man
man 5 passwd

4.快捷键：
ctrl + c：停止进程

ctrl + l：清屏

ctrl + r：搜索历史命令

ctrl + q：退出

5.善于用tab键

## sz rz

上传文件到linux上, 是上传到当前所在的目录下
yum list|grep lrzsz
sudo yum -y install lrzsz.x86_64
命令:(参数 -y 如果linux上有相同的文件, 会覆盖)
	rz
	rz -y

##

linux的命令操作


1、日常操作命令  

**查看当前所在的工作目录
pwd

**查看当前系统的时间 
date

**查看有谁在线（哪些人登陆到了服务器）
who  查看当前在线
last 查看最近的登陆历史记录


2、文件系统操作
**
ls /    查看根目录下的子节点（文件夹和文件）信息
ls -al  -a是显示隐藏文件   -l是以更详细的列表形式显示

**切换目录
cd  /home

**创建文件夹
mkdir aaa     这是相对路径的写法 
mkdir -p aaa/bbb/ccc
mkdir  /data    这是绝对路径的写法 

**删除文件夹
rmdir   可以删除空目录
rm -r aaa   可以把aaa整个文件夹及其中的所有子节点全部删除
rm -rf aaa   强制删除aaa

**修改文件夹名称
mv aaa angelababy

**创建文件
touch  somefile.1   创建一个空文件
echo "i miss you,my baby" > somefile.2  利用重定向“>”的功能，将一条指令的输出结果写入到一个文件中，会覆盖原文件内容
echo "huangxiaoming ,gun dan" >> somefile.2     将一条指令的输出结果追加到一个文件中，不会覆盖原文件内容

用vi文本编辑器来编辑生成文件
******最基本用法
vi  somefile.4
1、首先会进入“一般模式”，此模式只接受各种快捷键，不能编辑文件内容
2、按i键，就会从一般模式进入编辑模式，此模式下，敲入的都是文件内容
3、编辑完成之后，按Esc键退出编辑模式，回到一般模式；
4、再按：，进入“底行命令模式”，输入wq命令，回车即可

******一些常用快捷键
一些有用的快捷键（在一般模式下使用）：
a  在光标后一位开始插入
A   在该行的最后插入
I   在该行的最前面插入
gg   直接跳到文件的首行
G    直接跳到文件的末行
dd   删除行，如果  5dd   ，则一次性删除光标后的5行
yy  复制当前行,  复制多行，则  3yy，则复制当前行附近的3行
p   粘贴
v  进入字符选择模式，选择完成后，按y复制，按p粘贴
ctrl+v  进入块选择模式，选择完成后，按y复制，按p粘贴
shift+v  进入行选择模式，选择完成后，按y复制，按p粘贴

查找并替换（在底行命令模式中输入）
%s/sad/88888888888888     效果：查找文件中所有sad，替换为88888888888888
/you       效果：查找文件中出现的you，并定位到第一个找到的地方，按n可以定位到下一个匹配位置（按N定位到上一个）


3、文件权限的操作

****linux文件权限的描述格式解读
drwxr-xr-x      （也可以用二进制表示  111 101 101  -->  755）

d：标识节点类型（d：文件夹   -：文件  l:链接）
r：可读   w：可写    x：可执行 
第一组rwx：  表示这个文件的拥有者对它的权限：可读可写可执行
第二组r-x：  表示这个文件的所属组对它的权限：可读，不可写，可执行
第三组r-x：  表示这个文件的其他用户（相对于上面两类用户）对它的权限：可读，不可写，可执行


****修改文件权限
chmod g-rw haha.dat    表示将haha.dat对所属组的rw权限取消
chmod o-rw haha.dat 	表示将haha.dat对其他人的rw权限取消
chmod u+x haha.dat      表示将haha.dat对所属用户的权限增加x

也可以用数字的方式来修改权限
chmod 664 haha.dat   
就会修改成   rw-rw-r--

如果要将一个文件夹的所有内容权限统一修改，则可以-R参数
chmod -R 770 aaa/
chown angela:angela aaa/    <只有root能执行>

目录没有执行权限的时候普通用户不能进入
文件只有读写权限的时候普通用户是可以删除的(删除文件不是修改它,是操作父及目录),只要父级目录有执行和修改的权限




5、系统管理操作
*****查看主机名
hostname
****修改主机名(重启后无效)
hostname hadoop

*****修改主机名(重启后永久生效)
vi /ect/sysconfig/network
****修改IP(重启后无效)
ifconfig eth0 192.168.12.22

****修改IP(重启后永久生效)
vi /etc/sysconfig/network-scripts/ifcfg-eth0


mount ****  挂载外部存储设备到文件系统中
mkdir   /mnt/cdrom      创建一个目录，用来挂载
mount -t iso9660 -o ro /dev/cdrom /mnt/cdrom/     将设备/dev/cdrom挂载到 挂载点 ：  /mnt/cdrom中

*****umount
umount /mnt/cdrom


*****统计文件或文件夹的大小
du -sh  /mnt/cdrom/Packages
df -h    查看磁盘的空间
****关机
halt
****重启
reboot


******配置主机之间的免密ssh登陆
假如 A  要登陆  B
在A上操作：
ssh-keygen   (提示时，直接回车即可)
ssh-copy-id   B(可以使用IP或者主机名)


系统信息 
arch 显示机器的处理器架构(1) 
uname -m 显示机器的处理器架构(2) 
uname -r 显示正在使用的内核版本 
dmidecode -q 显示硬件系统部件 - (SMBIOS / DMI) 
hdparm -i /dev/hda 罗列一个磁盘的架构特性 
hdparm -tT /dev/sda 在磁盘上执行测试性读取操作 
cat /proc/cpuinfo 显示CPU info的信息 
cat /proc/interrupts 显示中断 
cat /proc/meminfo 校验内存使用 
cat /proc/swaps 显示哪些swap被使用 
cat /proc/version 显示内核的版本 
cat /proc/net/dev 显示网络适配器及统计 
cat /proc/mounts 显示已加载的文件系统 
lspci -tv 罗列 PCI 设备 
lsusb -tv 显示 USB 设备 
date 显示系统日期 
cal 2007 显示2007年的日历表 
date 041217002007.00 设置日期和时间 - 月日时分年.秒 
clock -w 将时间修改保存到 BIOS 



关机 (系统的关机、重启以及登出 ) 
shutdown -h now 关闭系统(1) 
init 0 关闭系统(2) 
telinit 0 关闭系统(3) 
shutdown -h hours:minutes & 按预定时间关闭系统 
shutdown -c 取消按预定时间关闭系统 
shutdown -r now 重启(1) 
reboot 重启(2) 
logout 注销 



文件和目录 
cd /home 进入 '/ home' 目录' 
cd .. 返回上一级目录 
cd ../.. 返回上两级目录 
cd 进入个人的主目录 
cd ~user1 进入个人的主目录 
cd - 返回上次所在的目录 
pwd 显示工作路径 
ls 查看目录中的文件 
ls -F 查看目录中的文件 
ls -l 显示文件和目录的详细资料 
ls -a 显示隐藏文件 
ls *[0-9]* 显示包含数字的文件名和目录名 
tree 显示文件和目录由根目录开始的树形结构(1) 
lstree 显示文件和目录由根目录开始的树形结构(2) 
mkdir dir1 创建一个叫做 'dir1' 的目录' 
mkdir dir1 dir2 同时创建两个目录 
mkdir -p /tmp/dir1/dir2 创建一个目录树 
rm -f file1 删除一个叫做 'file1' 的文件' 
rmdir dir1 删除一个叫做 'dir1' 的目录' 
rm -rf dir1 删除一个叫做 'dir1' 的目录并同时删除其内容 
rm -rf dir1 dir2 同时删除两个目录及它们的内容 
mv dir1 new_dir 重命名/移动 一个目录 
cp file1 file2 复制一个文件 
cp dir/* . 复制一个目录下的所有文件到当前工作目录 
cp -a /tmp/dir1 . 复制一个目录到当前工作目录 
cp -a dir1 dir2 复制一个目录 
ln -s file1 lnk1 创建一个指向文件或目录的软链接 
ln file1 lnk1 创建一个指向文件或目录的物理链接 
touch -t 0712250000 file1 修改一个文件或目录的时间戳 - (YYMMDDhhmm) 
file file1 outputs the mime type of the file as text 
iconv -l 列出已知的编码 
iconv -f fromEncoding -t toEncoding inputFile > outputFile creates a new from the given input file by assuming it is encoded in fromEncoding and converting it to toEncoding. 
find . -maxdepth 1 -name *.jpg -print -exec convert "{}" -resize 80x60 "thumbs/{}" \; batch resize files in the current directory and send them to a thumbnails directory (requires convert from Imagemagick) 



文件搜索 
find / -name file1 从 '/' 开始进入根文件系统搜索文件和目录 
find / -user user1 搜索属于用户 'user1' 的文件和目录 
find /home/user1 -name \*.bin 在目录 '/ home/user1' 中搜索带有'.bin' 结尾的文件 
find /usr/bin -type f -atime +100 搜索在过去100天内未被使用过的执行文件 
find /usr/bin -type f -mtime -10 搜索在10天内被创建或者修改过的文件 
find / -name \*.rpm -exec chmod 755 '{}' \; 搜索以 '.rpm' 结尾的文件并定义其权限 
find / -xdev -name \*.rpm 搜索以 '.rpm' 结尾的文件，忽略光驱、捷盘等可移动设备 
locate \*.ps 寻找以 '.ps' 结尾的文件 - 先运行 'updatedb' 命令 
whereis halt 显示一个二进制文件、源码或man的位置 
which halt 显示一个二进制文件或可执行文件的完整路径 



挂载一个文件系统 



磁盘空间 
df -h 显示已经挂载的分区列表 
ls -lSr |more 以尺寸大小排列文件和目录 
du -sh dir1 估算目录 'dir1' 已经使用的磁盘空间' 
du -sk * | sort -rn 以容量大小为依据依次显示文件和目录的大小 
rpm -q -a --qf '%10{SIZE}t%{NAME}n' | sort -k1,1n 以大小为依据依次显示已安装的rpm包所使用的空间 (fedora, redhat类系统) 
dpkg-query -W -f='${Installed-Size;10}t${Package}n' | sort -k1,1n 以大小为依据显示已安装的deb包所使用的空间 (ubuntu, debian类系统) 



用户和群组 
groupadd group_name 创建一个新用户组 
groupdel group_name 删除一个用户组 
groupmod -n new_group_name old_group_name 重命名一个用户组 
useradd -c "Name Surname " -g admin -d /home/user1 -s /bin/bash user1 创建一个属于 "admin" 用户组的用户 
useradd user1 创建一个新用户 
userdel -r user1 删除一个用户 ( '-r' 排除主目录) 
usermod -c "User FTP" -g system -d /ftp/user1 -s /bin/nologin user1 修改用户属性 
passwd 修改口令 
passwd user1 修改一个用户的口令 (只允许root执行) 
chage -E 2005-12-31 user1 设置用户口令的失效期限 
pwck 检查 '/etc/passwd' 的文件格式和语法修正以及存在的用户 
grpck 检查 '/etc/passwd' 的文件格式和语法修正以及存在的群组 
newgrp group_name 登陆进一个新的群组以改变新创建文件的预设群组 



文件的权限 - 使用 "+" 设置权限，使用 "-" 用于取消 
ls -lh 显示权限 
ls /tmp | pr -T5 -W$COLUMNS 将终端划分成5栏显示 
chmod ugo+rwx directory1 设置目录的所有人(u)、群组(g)以及其他人(o)以读（r ）、写(w)和执行(x)的权限 
chmod go-rwx directory1 删除群组(g)与其他人(o)对目录的读写执行权限 
chown user1 file1 改变一个文件的所有人属性 
chown -R user1 directory1 改变一个目录的所有人属性并同时改变改目录下所有文件的属性 
chgrp group1 file1 改变文件的群组 
chown user1:group1 file1 改变一个文件的所有人和群组属性 
find / -perm -u+s 罗列一个系统中所有使用了SUID控制的文件 
chmod u+s /bin/file1 设置一个二进制文件的 SUID 位 - 运行该文件的用户也被赋予和所有者同样的权限 
chmod u-s /bin/file1 禁用一个二进制文件的 SUID位 
chmod g+s /home/public 设置一个目录的SGID 位 - 类似SUID ，不过这是针对目录的 
chmod g-s /home/public 禁用一个目录的 SGID 位 
chmod o+t /home/public 设置一个文件的 STIKY 位 - 只允许合法所有人删除文件 
chmod o-t /home/public 禁用一个目录的 STIKY 位 



文件的特殊属性 - 使用 "+" 设置权限，使用 "-" 用于取消 
chattr +a file1 只允许以追加方式读写文件 
chattr +c file1 允许这个文件能被内核自动压缩/解压 
chattr +d file1 在进行文件系统备份时，dump程序将忽略这个文件 
chattr +i file1 设置成不可变的文件，不能被删除、修改、重命名或者链接 
chattr +s file1 允许一个文件被安全地删除 
chattr +S file1 一旦应用程序对这个文件执行了写操作，使系统立刻把修改的结果写到磁盘 
chattr +u file1 若文件被删除，系统会允许你在以后恢复这个被删除的文件 
lsattr 显示特殊的属性 



打包和压缩文件 
bunzip2 file1.bz2 解压一个叫做 'file1.bz2'的文件 
bzip2 file1 压缩一个叫做 'file1' 的文件 
gunzip file1.gz 解压一个叫做 'file1.gz'的文件 
gzip file1 压缩一个叫做 'file1'的文件 
gzip -9 file1 最大程度压缩 
rar a file1.rar test_file 创建一个叫做 'file1.rar' 的包 
rar a file1.rar file1 file2 dir1 同时压缩 'file1', 'file2' 以及目录 'dir1' 
rar x file1.rar 解压rar包 
unrar x file1.rar 解压rar包 
tar -cvf archive.tar file1 创建一个非压缩的 tarball 
tar -cvf archive.tar file1 file2 dir1 创建一个包含了 'file1', 'file2' 以及 'dir1'的档案文件 
tar -tf archive.tar 显示一个包中的内容 
tar -xvf archive.tar 释放一个包 
tar -xvf archive.tar -C /tmp 将压缩包释放到 /tmp目录下 
tar -cvfj archive.tar.bz2 dir1 创建一个bzip2格式的压缩包 
tar -xvfj archive.tar.bz2 解压一个bzip2格式的压缩包 
tar -cvfz archive.tar.gz dir1 创建一个gzip格式的压缩包 
tar -xvfz archive.tar.gz 解压一个gzip格式的压缩包 
zip file1.zip file1 创建一个zip格式的压缩包 
zip -r file1.zip file1 file2 dir1 将几个文件和目录同时压缩成一个zip格式的压缩包 
unzip file1.zip 解压一个zip格式压缩包 



RPM 包 - （Fedora, Redhat及类似系统） 
rpm -ivh package.rpm 安装一个rpm包 
rpm -ivh --nodeeps package.rpm 安装一个rpm包而忽略依赖关系警告 
rpm -U package.rpm 更新一个rpm包但不改变其配置文件 
rpm -F package.rpm 更新一个确定已经安装的rpm包 
rpm -e package_name.rpm 删除一个rpm包 
rpm -qa 显示系统中所有已经安装的rpm包 
rpm -qa | grep httpd 显示所有名称中包含 "httpd" 字样的rpm包 
rpm -qi package_name 获取一个已安装包的特殊信息 
rpm -qg "System Environment/Daemons" 显示一个组件的rpm包 
rpm -ql package_name 显示一个已经安装的rpm包提供的文件列表 
rpm -qc package_name 显示一个已经安装的rpm包提供的配置文件列表 
rpm -q package_name --whatrequires 显示与一个rpm包存在依赖关系的列表 
rpm -q package_name --whatprovides 显示一个rpm包所占的体积 
rpm -q package_name --scripts 显示在安装/删除期间所执行的脚本l 
rpm -q package_name --changelog 显示一个rpm包的修改历史 
rpm -qf /etc/httpd/conf/httpd.conf 确认所给的文件由哪个rpm包所提供 
rpm -qp package.rpm -l 显示由一个尚未安装的rpm包提供的文件列表 
rpm --import /media/cdrom/RPM-GPG-KEY 导入公钥数字证书 
rpm --checksig package.rpm 确认一个rpm包的完整性 
rpm -qa gpg-pubkey 确认已安装的所有rpm包的完整性 
rpm -V package_name 检查文件尺寸、 许可、类型、所有者、群组、MD5检查以及最后修改时间 
rpm -Va 检查系统中所有已安装的rpm包- 小心使用 
rpm -Vp package.rpm 确认一个rpm包还未安装 
rpm2cpio package.rpm | cpio --extract --make-directories *bin* 从一个rpm包运行可执行文件 
rpm -ivh /usr/src/redhat/RPMS/`arch`/package.rpm 从一个rpm源码安装一个构建好的包 
rpmbuild --rebuild package_name.src.rpm 从一个rpm源码构建一个 rpm 包 



YUM 软件包升级器 - （Fedora, RedHat及类似系统） 
yum install package_name 下载并安装一个rpm包 
yum localinstall package_name.rpm 将安装一个rpm包，使用你自己的软件仓库为你解决所有依赖关系 
yum update package_name.rpm 更新当前系统中所有安装的rpm包 
yum update package_name 更新一个rpm包 
yum remove package_name 删除一个rpm包 
yum list 列出当前系统中安装的所有包 
yum search package_name 在rpm仓库中搜寻软件包 
yum clean packages 清理rpm缓存删除下载的包 
yum clean headers 删除所有头文件 
yum clean all 删除所有缓存的包和头文件 



DEB 包 (Debian, Ubuntu 以及类似系统) 


APT 软件工具 (Debian, Ubuntu 以及类似系统) 
apt-get install package_name 安装/更新一个 deb 包 
apt-cdrom install package_name 从光盘安装/更新一个 deb 包 
apt-get update 升级列表中的软件包 
apt-get upgrade 升级所有已安装的软件 
apt-get remove package_name 从系统删除一个deb包 
apt-get check 确认依赖的软件仓库正确 
apt-get clean 从下载的软件包中清理缓存 
apt-cache search searched-package 返回包含所要搜索字符串的软件包名称 



查看文件内容 
cat file1 从第一个字节开始正向查看文件的内容 
tac file1 从最后一行开始反向查看一个文件的内容 
more file1 查看一个长文件的内容 
less file1 类似于 'more' 命令，但是它允许在文件中和正向操作一样的反向操作 
head -2 file1 查看一个文件的前两行 
tail -2 file1 查看一个文件的最后两行 


文本处理 




字符设置和文件格式转换 


文件系统分析 



初始化一个文件系统 


SWAP文件系统 

备份 



光盘 



网络 - （以太网和WIFI无线） 
ifconfig eth0 显示一个以太网卡的配置 