CentOS6.5下netcat工具安装教程
 
1.下载
下载地址：http://sourceforge.net/projects/netcat/files/netcat/0.7.1/
下载的是netcat-0.7.1.tar.gz版本
 
2.拷贝
用U盘拷贝到/home/Hadoop目录下
进行解压：
cd /home/hadoop 
tar -zxvf netcat-0.7.1.tar.gz -C /usr/local
改名：
cd /usr/local
mv netcat-0.7.1 netcat
 
3.安装
切换目录：
cd /usr/local/netcat
配置，把文件存放在/opt/netcat下，删除时，卸载软件时，只要删除这个文件就行了：
./configure --prefix=/opt/netcat
编译：
make
安装：
make install
 
4.配置
vim /etc/profile
添加以下内容：
# set  netcat path
export NETCAT_HOME=/opt/netcat
export PATH=$PATH:$NETCAT_HOME/bin
保存，退出，并使配置生效：
source /etc/profile
 
5.检验
nc -help成功
