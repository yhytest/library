## 线上查询及帮助命令 (2 个)

* man 查看命令帮助
* help 查看 Linux 内置命令的帮助
## 文件和目录操作命令 (18 个)

* ls list，列出目录的信息。
* cd change directory，切换到指定目录。
* cp  copy，复制文件或目录。
* find 用于查找目录及目录下的文件。
* mkdir  make directories，创建目录。
* mv  move，移动或重命名文件。
* pwd print working directory，显示当前工作目录的绝对路径。
* rename 用于重命名文件。
* rm remove，删除一个或多个文件或目录。
* rmdir remove empty directories，删除空目录。
* touch 创建新的空文件
* tree 以树形结构显示目录下的内容。
* basename 显示文件名或目录名。
* dirname 显示文件或目录路径。
* chattr 改变文件的扩展属性。
* lsattr 查看文件扩展属性。
* file 显示文件的类型。
* md5sum 计算和校验文件的 MD5 值。
## 查看文件及内容处理命令（21 个）

* cat concatenate，用于连接多个文件并且打印到屏幕输出或重定向到指定文件中。
* tac tac 是 cat 的反向拼写，因此命令的功能为反向显示文件内容。
* more 分页显示文件内容。
* less 分页显示文件内容，more 命令的相反用法。
* head 显示文件内容的头部。
* tail 显示文件内容的尾部。
* cut 将文件的每一行按指定分隔符分割并输出。
* split 分割文件为不同的小片段。
* paste 按行合并文件内容。
* sort 对文件的文本内容排序。
* uniq 去除重复行。
* wc 统计文件的行数、单词数或字节数。
* iconv 转换文件的编码格式。
* dos2unix 将 DOS 格式文件转换成 UNIX 格式。
* diff difference，比较文件的差异，常用于文本文件。
* vimdiff 命令行可视化文件比较工具，常用于文本文件。
* rev 反向输出文件内容。
* grep/egrep 过滤字符串
* join 按两个文件的相同字段合并。
* tr 替换或删除字符。
* vi/vim 命令行文本编辑器。
##文件压缩及解压缩命令（4 个）

* tar 打包压缩。
* unzip 解压文件。
* gzip gzip 压缩工具。
* zip 压缩工具。
## 信息显示命令（11 个）

* uname 显示操作系统相关信息的命令。
* hostname 显示或者设置当前系统的主机名。
* dmesg 显示开机信息，用于诊断系统故障。
* uptime 显示系统运行时间及负载。
* stat 显示文件或文件系统的状态。
* du 计算磁盘空间使用情况。
* df 报告文件系统磁盘空间的使用情况。
* top 实时显示系统资源使用情况。
* free 查看系统内存。
* date 显示与设置系统时间。
* cal 查看日历等时间信息。
## 搜索文件命令（4 个）

* which 查找二进制命令，按环境变量 PATH 路径查找。
* find 从磁盘遍历查找文件或目录。
* whereis 查找二进制命令，按环境变量 PATH 路径查找。
* locate 从数据库查找命令，使用 updatedb 更新库。
## 用户管理命令（10 个）

* useradd 添加用户。
* usermod 修改系统已经存在的用户属性。
* userdel 删除用户。
* groupadd 添加用户组。
* passwd 修改用户密码。
* chage 修改用户密码有效期限。
* id 查看用户的 uid,gid 及归属的用户组。
* su 切换用户身份。
* visudo 编辑 / etc/sudoers 文件的专属命令。
* sudo 以另外一个用户身份（默认 root 用户）执行
## 基础网络操作命令（11 个）

* telnet 使用 TELNET 协议远程登录。
* ssh 使用 SSH 加密协议远程登录。
* scp secure copy，用于不同主机之间复制文件。
* wget 命令行下载文件。
* ping 测试主机之间网络的连通性。
* route 显示和设置 linux 系统的路由表。
* ifconfig 查看、配置、启用或禁用网络接口的命令。
* ifup 启动网卡。
* ifdown 关闭网卡。
* netstat 查看网络状态。
* ss 查看网络状态。
## 深入网络操作命令（9 个）

* nmap 网络扫描命令。
* lsof list open files，也就是列举系统中已经被打开的文件。
* mail 发送和接收邮件。
* mutt 邮件管理命令。
* nslookup 交互式查询互联网 DNS 服务器的命令。
* dig 查找 DNS 解析过程。
* host 查询 DNS 的命令。
* traceroute 追踪数据传输路由状况。
* tcpdump 命令行的抓包工具。
## 有关磁盘与文件系统的命令（16 个）

* mount 挂载文件系统。
* umoun 卸载文件系统。
* fsck 检查并修复 Linux 文件系统。
* dd 转换或复制文件。
* dumpe2fs 导出 ext2/ext3/ext4 文件系统信息。
* dump ext2/3/4 文件系统备份工具。
* fdisk 磁盘分区命令，适用于 2TB 以下磁盘分区。
* parted 磁盘分区命令，没有磁盘大小限制，常用于 2TB 以下磁盘分区。
* mkfs 格式化创建 Linux 文件系统。
* partprobe 更新内核的硬盘分区表信息。
* e2fsck 检查 ext2/ext3/ext4 类型文件系统。
* mkswap 创建 Linux 交换分区。
* swapon 启用交换分区。
* swapoff 关闭交换分区。
* sync 将内存缓冲区内的数据写入磁盘。
* resize2fs 调整 ext2/ext3/ext4 文件系统大小。
##系统权限及用户授权相关命令（4 个）

* chmod 改变文件或目录权限。
* chown 改变文件或目录的属主和属组。
* chgrp 更改文件用户组。
* umask 显示或设置权限掩码。
## 查看系统用户登陆信息的命令（7 个）

* whoami 显示当前有效的用户名称，相当于执行 id -un 命令。
* who 显示目前登录系统的用户信息。
* w 显示已经登陆系统的用户列表，并显示用户正在执行的指令。
* last 显示登入系统的用户。
* lastlog 显示系统中所有用户最近一次登录信息。
* users 显示当前登录系统的所有用户的用户列表。
* finger 查找并显示用户信息。
## 内置命令及其它（19 个）

* echo 打印变量，或直接输出指定的字符串
* printf 将结果格式化输出到标准输出。
* rpm 管理 rpm 包的命令。
* yum 自动化简单化地管理 rpm 包的命令。
* watch 周期性的执行给定的命令，并将命令的输出以全屏方式显示。
* alias 设置系统别名。
* unalias 取消系统别名。
* date 查看或设置系统时间。
* clear 清除屏幕，简称清屏。
* history 查看命令执行的历史纪录。
* eject 弹出光驱。
* time 计算命令执行时间。
* nc 功能强大的网络工具。
* xargs 将标准输入转换成命令行参数。
* exec 调用并执行指令的命令。
* export 设置或者显示环境变量。
* unset 删除变量或函数。
* type 用于判断另外一个命令是否是内置命令。
* bc 命令行科学计算器
##系统管理与性能监视命令 (9 个)

* chkconfig 管理 Linux 系统开机启动项。
* vmstat 虚拟内存统计。
* mpsta 显示各个可用 CPU 的状态统计。
* iostat 统计系统 IO。
* sar 全面地获取系统的 CPU和网络等性能数据。
* ipcs 用于报告 Linux 中进程间通信设施的状态
* ipcrm 用来删除一个或更多的消息队列、信号量集或者共享内存标识。
* strace 用于诊断、调试 Linux 用户空间跟踪器。
* ltrace 命令会跟踪进程的库函数调用, 它会显现出哪个库函数被调用。
## 关机 / 重启 / 注销和查看系统信息的命令（6 个）

* shutdown 关机。
* halt 关机。
* poweroff 关闭电源。
* logout 退出当前登录的 Shell。
* exit 退出当前登录的 Shell。
* Ctrl+d 退出当前登录的 Shell 的快捷键。
## 进程管理相关命令（15 个）

* bg 将一个在后台暂停的命令，在后台执行
* fg 将后台中的命令调至前台继续运行。
* jobs 查看当前有多少在后台运行的命令。
* kill 终止进程。
* killall 通过进程名终止进程。
* pkill 通过进程名终止进程。
* crontab 定时任务命令。
* ps 显示进程的快照。
* pstree 树形显示进程。
* nice/renice 调整程序运行的优先级。
* nohup 忽略挂起信号运行指定的命令。
* pgrep 查找匹配条件的进程。
* runlevel 查看系统当前运行级别。
* init 切换运行级别。
* service 启动、停止、重新启动和关闭系统服务
* ctrl + c：停止进程
* ctrl + l：清屏
* ctrl + r：搜索历史命令
* ctrl + q：退出
* 善于用tab键

## 文件内容查看

* cat 连接文件并打印到标准输出设备上，cat经常用来显示文件的内容。
* grep 在指定的文本文件中查找指定的字符串
* tail 输出文件中的尾部内容
* head 显示文件的开头的内容。
* more 一个基于vi编辑器文本过滤器，
* less 与more十分相似，都可以用来浏览文字档案的内容，
* wc 用来计算数字。
* tr 对来自标准输入的字符进行替换、压缩和删除。
* sort 将文件进行排序，并将排序结果标准输出。
* find 在指定目录下查找文件。
* which 查找并显示给定命令的绝对路径
* whereis 用来定位指令的二进制程序、源代码文件和man手册页等相关文件的路径。
* locate 其实是find -name的另一种写法
* tar tar命令可以为linux的文件和目录创建档案。
* zip 可以用来解压缩文件，或者对文件进行打包操作。
* unzip 加压缩.zip包，不在详述。


## Java常用工具

* java  可用来执行jar包。
* jps  查看当前Java进程
* jmap 打印java进程内存中所有‘对象’的情况。
* jstat 监控JVM
* jstack  打印给定java进程ID

## 进程控制和系统命令

* su 用于切换当前用户身份到其他用户身份
* sudo 以其他身份来执行命令，预设的身份为root。
* ps 列出当前系统进程
* kill 杀死某个进程
* date 查看当前系统的时间 
* watch 以周期性的方式执行给定的指令，指令输出以全屏方式显示。
* service 显示所有系统服务的当前状态。
* who  查看当前在线
* last 查看最近的登陆历史记录
* kill -9 4333 强制杀死pid(进程号)
* kill -9 java 强制杀死所有的Java进程
* date 显示系统日期 
* cal 2007 显示2007年的日历表 
* df 查看硬盘使用情况
* du 查看文件大小
* top 可以实时动态地查看系统的整体运行情况
* free 显示当前系统未使用的和已使用的内存数目
* lsof命令用于查看你进程开打的文件
* ulimit  用来限制系统用户对shell资源的访问   
* vmstat 显示虚拟内存状态
* iostat  监视系统输入输出设备和CPU的使用情况
* shutdown 关机
* reboot 重启 
* logout 注销 

## 文件有关

* mkdir test 创建一个test的文件夹
* mkdir dir1 dir2 同时创建两个目录 
* mkdir test/{src,WebRoot} 在test目录下创建src和WebRoot两个文件夹
* touch  a.txt   创建一个空文件
* touch  a.txt b.txt 创建一个空文件同时创建2个文件
* touch {a.txt b.txt} 创建一个空文件同时创建2个文件
* cp a.txt b.txt 
* cp -r /test1 /test2  拷贝/test1目录下的所有文件到/test2
* cp -a dir1 dir2 复制一个目录 
* rm -rf test/*.txt   强制删除test文件夹以及txt文件
* mv a.txt  b.txt 将a.txt改名为b.txt
* mv a.txt  test  将a.txt移动到test

**输入输出重定向**

* cat >> file1 追加内容
* cat > file1  覆盖内容

**软连接（快捷方式）**

* ln –s  /var/www/test  test 创建目录 /var/www/test  软链接test
* ln –snf  /var/www/test1    修改软链接test指向的目录为/var/www/test1
* rm –rf test 删除软链接test
   
## 3.用户管理
**用户名**

* useradd uname1 创建用户名
* usermod -l 新名 原名 修改用户名 
* userdel uname1 删除用户名

**用户组**

* groupadd grp1 创建用户组grp1   
* groupmod -n 新名 原名
* groupdel grp1 删除用户组grp1

**密码**

* passwd 密码 设置密码 
	

**切换用户** 

* su - uname1 切换到用户uname1

##查看文件内容 

* cat file1 正向查看文件的全部内容 
* tac file1 反向查看文件的全部内容 
* more file1 正向查看文件的%n内容 
* less file1 反向查看文件的%n内容 
* head -2 file1 查看一个文件的前两行 
* tail -2 file1 查看一个文件的最后两行 
* wc -w README 查看一下README文件有多单词
* wc -l README 查看一下README文件多少个少行
* stat a.txt 查看文件详情

##文件搜索 

* find / -name '*.java' 从 '/' 开始查找,根据name,查找*.java文件 
* find / -user '*.java' 从 '/' 开始查找,根据user,查找*.java文件
* locate hadoop.txt 查找文件(需要更新库索引:updatedb)
* awk -F: '/root/' /etc/passwd 搜索/etc/passwd有root关键字的所有行
* sed -i "s/&&/&/g" grep && -rl a.txt  把 a.txt文件中的&& 替换为&

##定时作业crontab

* cat /etc/contab  查看contab
* crontab -e uname 新建crontab文件
* crontab -l file1 列出crontab文件
* crontab -e file1 编辑crontab文件
* crontab -r file1 删除crontab文件

##文件压缩与解压 

* bzip2/bunzip2 file1 压缩/解压(类型*.bzip2)
* gzip/gunzip file1 压缩/解压(类型*.gzip)
* zip/unzip 压缩/解压(类型*.zip)
* rar/unrar x file1.rar 压缩/解压(类型*.rar)
* compress/uncompress 压缩/解压(类型*.Z)
* tar -zcvf archive.tar.gz dir1 创建一个gzip格式的压缩包 压缩到dir1
* tar -zxvf archive.tar.gz -C dir1 解压一个gzip格式的压缩包 解压到dir1

##Linux权限操作

* 三种基本权限 r 可读（read） w 可写（write）x 可执行 （execute）
* chmod 777 a.txt    给a.txt赋所有权限
* chmod -R 777 dir1/  给dir1下所有文件赋限
* chown user1 file1 改变一个文件的所有人属性
* chown -R user1 directory1 改变一个目录的所有人属性并同时改变改目录下所有文件的属性 
* chgrp group1 file1 改变文件的群组  

##网络与工具

* netstat 显示网络状态信息
* ifconfig eth0 网卡网络配置详解 
* ping 测试网络的连通性
* hostname 查看主机名
* vi /ect/sysconfig/network 修改主机名(重启后永久生效)
* vi /etc/sysconfig/network-scripts/ifcfg-eth0  修改IP(重启后永久生效)
* curl  curl命令是一个利用URL规则在命令行下工作的文件传输工具。
* telnet  常用它来检测端口。
* nslookup 查DNS信息用的命令。
* ss 用来显示处于活动状态的套接字信息。
* nc 用来设置路由器
**iptables**

* service iptables status 查看iptables状态
* service iptables start/stop 开启/关闭iptables
* chkconfig iptables --list 查看iptables是否开机启动
* chkconfig iptables on/off 设置iptables开机启动/不启动

**后台服务管理**

* service network status   查看指定服务的状态
* service network stop     停止指定服务
* service network start    启动指定服务
* service network restart  重启指定服务
* service --status-all  查看系统中所有的后台服务

**设置后台服务的自启配置**

* chkconfig   查看所有服务器自启配置
* chkconfig iptables off   关掉指定服务的自动启动
* chkconfig iptables on   开启指定服务的自动启动

## 软件安装

**rpm安装，升级，卸载**

* rpm -ivh package 安装package 
* rpm -Uvh package 升级package
* rpm -qa |grep jdk  查找jdk   
* rpm -e jdk 卸载jdk

**yum安装，升级，卸载**

* yum  install  gcc-c++  安装gcc
* yum  update  gcc-c++   升级gcc
* yum  remove  gcc-c++   卸载gcc
 
**apt安装，升级，卸载**

* apt-get install package 安装package
* apt-get update package 升级package
* apt-get upgrade 升级所有软件 
* apt-get remove package 卸载package 

**安装JDK**

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
		
**安装tomcat**

	tar -zxvf /soft/apache-tomcat-7.0.47.tar.gz -C /programs/
	cd /programs/apache-tomcat-7.0.47/bin/
	./startup.sh





	

	





