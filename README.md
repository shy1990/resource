# resource
1.ubuntu挂载硬盘
df -h    查看挂载

umount /dev/sdb5 dev/sdb8 取消挂载

mkfs.ext4 /dev/sdb或mkfs -t ext4 /dev/sdb 把硬盘格式转化为ext4格式

fdisk /dev/sdb 分区
n 默认分区
p 主分区
1 进行分区
fdisk -lu 查看分区

sudo mount -t ext4 /dev/sdb /devdata 进行绑定

说明：
指定硬盘分区文件系统类型为ext4 ，同时将 /dev/sdb 分区挂载到目录 /devdata。

 
2.sudo chmod 777 virtualbox 设置权限
3.安装.tar.gz格式的软件：一，sudo tar zvxf filename
                                       二,sudo gedit  name.sh
4.打开系统监视器：gnome-system-monitor
5.rar解压工具安装方法：
 （1）安装 sudo apt-get install rar
          卸载 sudo apt-get remove rar
 （2） tar -xf jdk-8u144-linux-x64.tar.gz  解压 .tar.gz格式
6:搜狗突然不能输入汉字 fcitx restart       
7:查看当前ubuntu的版本：（1）sudo lsb_release -a  （2）cat /etc/issue
8卸载搜狗    （1）首先我们开始卸载搜狗输入法。

$sudo apt-get  remove  sogoupinyin

（2）接下来我们再清除搜狗输入法相关的配置文件。

$sudo apt-get  purge  sogoupinyin

（3）然后自动卸载安装搜狗时候附加安装的一些依赖等

sudo apt-get autoremove
9清楚安装残留

dpkg -l |grep ^rc|awk '{print $2}' |sudo xargs dpkg -P

10 安装mysql

11卸载刚安装ubuntu之后没用的软件
（1）sudo apt-get remove libreoffice-common  删除libreoffice，因为计算效率太差
 (2) sudo apt-get remove unity-webapps-common 删除Amazon链接
（3） sudo apt-get remove thunderbird totem rhythmbox empathy brasero simple-scan gnome-mahjongg aisleriot gnome-mines cheese transmission-common gnome-orca webbrowser-app gnome-sudoku landscape-client-ui-install
 sudo apt-get remove onboard deja-dup   删除基本不用的自带软件
 这样系统基本就干净了


安装rpm格式文件

    $sudo apt-get install alien ##alien默认没有安装，所以首先要安装它

    $sudo alien xxxx.rpm  ##将rpm转换为deb,完成后会生成一个xxxx.deb

    $sudo dpkg -i xxxx.deb ##这样xxxx软件就可以安装完成了
