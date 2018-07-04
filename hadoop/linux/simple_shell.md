##常用linux命令


    　　1、进入目录 cd /etc

    　　带斜杠的是绝对路径，如果不带，就是进入当前目录下的子目录。

    　　2、列举该目录结构 ls -al

    　　3、查看文件内容 cat /etc/hosts

    　　4、修改某个文件 vi /etc/hosts

     　　　　                vim /etc/hosts

    　　5、重启 reboot

    　　6、提权  su root

                      sudo

    　　7、开启服务 service ntpd start

    　　8、查看服务状态 service ntpd status

    　　9、关闭服务 service ntpd stop

    　　10、开机自启动 chkconfig ntpd on

    　　11、删除文件 rm /var/www/html/abc

    　　12、删除文件夹 rm -rf /var/www/html/aa

    　　13、SSH登陆 ssh root@H31

                             ssh h31

    　　14、修改文件，文件夹权限 chmod 700 /var/www/html/aa

    　　15、复制文件并改名 cat id_rsa.pub >>authorized_keys

    　　16、查看包状态  rpm -qa|grep ssh

    　　17、yum安装 yum install ssh

    　　18、拷贝文件、文件夹到其他机器 scp /root/.ssh root@H31:/root/.ssh/

    　　19、查看机器名 hostname

    　　20、查Ip等信息 ifconfig
