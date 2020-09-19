---
title: Linux笔记
tags:
  - Linux
id: 193
categories:
  - 笔记
date: 2016-10-05 10:29:06

---

VMware 使用桥接时，会占用局域网IP，NAT不会，host only不能连网

递归创建目录mkdir -p dir/b，rmdir并不怎么使用，删除目录使用rm -rf dir/

移动、重命名目录不需要额外的参数 mv
<!--more-->

复制目录需要cp -r，如果需要连目录的修改时间等属性一起复制cp -a，复制出来的就会和源一模一样

不推荐使用硬链接，使用软链接时，必须使用绝对路径，windows的Documents and Settings和Users使用的应该是联接mklink /J link target

updatedb命令用于更新locate搜索的数据库，搜索规则的配置文件在/etc/updatedb.conf

find / -iname ab.txt

find / -mtime -10

find / -size 10M

find / -size +20k -a -size -50k -exec ls -lh {} \;

常用目录:/etc/sysconfig/network-scripts/ifcfg-eth0  网卡配置

/etc/resolv.conf  DNS配置

下面是linux系统约定不同类型文件默认的颜色：
白色：表示普通文件
蓝色：表示目录
绿色：表示可执行文件
红色：表示压缩文件
浅蓝色：链接文件
红色闪烁：表示链接的文件有问题
黄色：表示设备文件

tar -zcvf a.tar.gz a

挂载光盘：mount /dev/sr0 /mnt/cd/

查看分区表：fdisk -l

挂载U盘：mount /dev/sdb1 /mnt/usb/

卸载文件系统：umount /mnt/cd

用户登录查看命令：w who last lastlog

! history ID 可以执行对应的历史命令

! history string 可以执行对应的最后一条历史命令

Ctrl + r 查找历史命令

ll &amp;&gt;&gt; 1.txt 无论正确错误都输出重定向

netstat -an ; route -n ; nslookup ;

tcpdump -i ens33 -nnX port 80  截获数据包

scp stx@192.168.164.137:/home/stx/t.txt ~   scp命令使用ssh来下载上传文件

ifup enp0s3(网卡名)  用于激活指定的网络接口。

命令结尾\，可以换行输入

source conf = . conf

目录权限只有0  5  7有用，其它无意义

pkill 进程名 ，杀死一组进程

jobs查看后台运行的进程

fg 工作号，可以恢复后台的进程到前台

nohup ./bin/node server.js &amp;  守护进程

cat /proc/cpuinfo   查看CPU信息  uname -a查看系统相关信息

htop 高级进程查看

rz sz 上传下载

systemctl status mysqld
which mysql
ps -aux|less
mysql -u root -p 123456
mysql -u root -p
service mariadb status
show databases;
mysql -u root -p
man source
help source
.
yum list|grep
yum list|less
ps -aux|less
kill 3712
man skill
skill 3712
systemctl restart mariadb 
reboot
man yum
yum list installed
yum list installed|less
service mysqld status
mysql restart
umask
whatis umask
netstat -an
netstat -an|less
ls /etc/profile
ls /etc/profile.d/
less .bash_profile 
less .bashrc 
a=1
b=2
c=$1:$2
echo $c
c=$a:$b
echo $c
less /etc/bashrc 
less /etc/profile
man export
whatis export
help export
export -p
less /etc/issue
less /etc/issue.net 
\
nestat -an
netstat -an
netstat -an | less
ll
cat path.txt 
sftp 
ll
chmod 400 nginx-1.6.2
ls nginx-1.6.2
ll
cd nginx-1.6.2
ll
cd ..
ll
chmod 700 nginx-1.6.2
ll
chmod 707 1.sh 
ll
chmod 707 anaconda-ks.cfg 
ll
chmod 700 anaconda-ks.cfg 
ll
chown www 1.sh 
ll
chmod 755 1.sh 
ll
visudo 
sudo -l
man sudo
visudo 
ll /usr/bin/passwd 
12356
ps -aux
pstree
pstree|less
top
free -h
top
kill -l
ps aux
vim /etc/hosts
wget mtn.com
less index.html 
ll /
jobs
ll
rm -rf index.html 
cd node-v8.6.0-linux-x64/
vim server.js
./bin/node server.js 
./bin/node server.js &
ps aux|grep node
pkill node
jobs
ps aux|grep node
vim server.js
./bin/node server.js &
jobs
wget [::1]:8000
wget http://[::1]:8000
less index.html 
wget ::1:8000
wget [::1]:8000
jobs
man jobs
pkill node
jobs
./bin/node server.js &
pkill node
./bin/node server.js
jobs
pkill node
jobs
ps aux|grep node
pkill node
ps aux|grep node
ps aux|grep node
man pkill
pkill -9 node
ps aux|grep node
jobs
d
jobs
./bin/node server.js
./bin/node server.js &
jobs
fg 1
jobs
fg
man fg
jobs
./bin/node server.js &
man touch
nohup 
nohup ./bin/node server.js &
jobs
cd node-v8.6.0-linux-x64/
nohup ./bin/node server.js &
job
jobs 
logout
jobs
ps -aux
ps -aux|less
top
ps aux|grep node
ps aux
ps aux|less
ps aux|grep node
vim initial-setup-ks.cfg 
ps aux|grep node
shutdown
shutdown now
cd node-v8.6.0-linux-x64/
man nohup.out
cat nohup.out
man nohup
vmstat 
dmesg
dmesg|grep cpu
dmesg|grep CPU
cat /proc/cpuinfo 
man cat
ll
cat LICENSE 
w
uname
uname -a
lsblk
man lsblk
man free
free
free -h
man free
file ./bin/node 
file ls
file /bin/ls
uptime 
uname
uname -a
cat /etc/centos-release
lsof 
lsof |grep node
lsof -c ./bin/node 
lsof -c sshd
service atd status
at 10
at 10s
at now + 10s
at 14:02
atq
at 14:0
at 14:04
date
atq
date
atq
jobs 
fg
pkill nod
pkill node
date
at 14:06
date
atq
date
jobs
fg
service crond status
man systemctl 
systemctl  list-units
systemctl  list-unit-files 
locate .vimrc
locate vimrc
vim README.md 
vim LICENSE 
du
du -sm /*
df -h
du -sk /*
du -sk /home
du -sk /home/*
du -sm /home/*
du -sh /home/*
du -sh /*
du -h /home/*
du -sh /home/*
wget www.ip138.com|less
less index.html
less index.html.1 
rm -rf index.html.1 
ifconfig
w
logout
fdisk -l
ls /dev
df -h
du -sh /*
fdisk /dev/sdb 
fdisk -l
mkdir /media/a
mount /dev/sdb1 /media/a
umount /dev/sdb1
ll /media/a
touch /media/a/1.txt
ll /media/a
df -h
df -ah
df -h
fdisk /dev/sdb
fdisk -l
mkdir /media/b 
vim /etc/fstab 
reboot
vim /etc/fstab 
reboot
/media/a/
ll /media/a/
df -h
fdisk -l
rm -rf /media/a/*
ll /media/a/
mkfs.ext4 /dev/sdb1 
mount /dev/sdb1 /media/a
df -h
mkfs
mount /dev/sdb2 /media/a
mkfs.ext4 /dev/sdb2 
umount /media/a
mkfs.ext4 /dev/sdb2 
ll /dev/sdb*
mkfs.ext4 /dev/sdb5
fdisk -l
mount /dev/sdb2 /media/a
mount /dev/sdb1 /media/a
mount /dev/sdb2 /media/b
mount /dev/sdb5 /media/b
df -h
mount /dev/sdb2 /media/b
df -h
fdisk -l
reboot
parted 
df -h
mount /dev/sdb1 /media/a
touch /media/a/1.txt
ll /media/a/1.txt
reboot
ll /media/a/
mount /dev/sdb1 /media/a
ll /media/a/
ll /media/a/lost+found/
ll /dev/sd*
fdisk -l
parted
df -h
/dev/sd*
sudo /dev/sd*
ll /dev/sd*
parted 
mkfs.ext4 /dev/sdc6
mkdir /media/c
mount /dev/sdc6 /media/c
df -h
parted
vim /etc/fstab 
reboot
df -h
fdisk -l
fdisk /dev/sdb5
fdisk /dev/sdb
df -h
df -ah
mkswap /dev/sdb5
free
free -h
swapon /dev/sdb5
free -h
df -h
fdisk -l
shutdown now
rm -rm /etc/nologin 
rm -rf /etc/nologin 
vim /etc/hosts
ping mtn.com
id root
id mtn
group mtn
groups mtn
chfn mtn
finger root
vim /etc/login.defs 
write root
write mtn
vim /etc/passwd
md5sum 
md5sum 123456
man md5sum
123456 | md5sum
12356 | sha1sum 
123 | sha1sum 
111 | sha1sum 
'123' | sha1sum 
sha1sum < '123'
sha1sum < 123
echo '123' | sha1sum
echo '123456' | sha1sum
echo '123' | sha1sum
echo 123 | sha1sum
vim /etc/passwd
vim /etc/skel/
ll /etc/skel/
ll-a /etc/skel/
ll -a /etc/skel/
java
java -version
vim /etc/login.defs 
vim /etc/default/useradd 
vim /etc/motd
exit
vim /etc/nologin
su mtn
exit
w
wc
who
less /etc/passwd
su mtn
shutdown now
crul
curl
curl qq.com
curl www.qq.com
curl baidu.com
shutdown
shutdown -n
shutdown -c
shutdown -s
w
curl "https://bootstrap.pypa.io/get-pip.py" -o "get-pip.py"
python --version
wd
pwd
pip install shadowsocks
python get-pip.py
pip install shadowsocks
vi /etc/shadowsocks.json
vi shadowsocks.json
vim /etc/shadowsocks.json
ssserver -c /etc/shadowsocks.json -d start
vim /etc/shadowsocks.json
ssserver -c /etc/shadowsocks.json -d start
ssserver -c /etc/shadowsocks.json -d stop
ssserver -c /etc/shadowsocks.json -d start
vim /etc/shadowsocks.json
ssserver -c /etc/shadowsocks.json -d restart
sh
ll
mkdir install-package
cd install-package/
wget https://fastdl.mongodb.org/linux/mongodb-linux-x86_64-3.0.6.tgz 
tar -zxvf mongodb-linux-x86_64-3.0.6.tgz
mv  mongodb-linux-x86_64-3.0.6/ /usr/local/mongodb
export PATH=/usr/local/mongodb/bin:$PATH
mkdir -p /data/db
./mongodb
mongodb
mongod
mongodb
mongo
mongod
cd /usr/local/mongodb/bin
./mongo
showdown -n
shutdown -h
shutdown /?
shutdown --help
shutdown -H