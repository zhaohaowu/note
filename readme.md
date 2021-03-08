##### 1、安装ubuntu18.04

https://blog.csdn.net/zhaohaowu/article/details/113749510

##### 2、安装chrome

https://www.google.cn/chrome/

##### 3、安装qq

https://im.qq.com/linuxqq/download.html

##### 4、安装录屏工具kazam

```
sudo apt-get install kazam
```

##### 5、安装截图软件深度截图

```
sudo apt install deepin-screenshot
```

##### 6、双系统时间同步

```
sudo apt-get install ntpdate
sudo ntpdate time.windows.com
sudo hwclock --localtime --systohc
```

##### 7、gedit永久显示行号

```
gsettings set org.gnome.gedit.preferences.editor display-line-numbers true
```

##### 8、安装&升级pip3

```
sudo apt-get install python3-pip
pip3 install --upgrade pip -i https://pypi.tuna.tsinghua.edu.cn/simple
```

##### 9、安装python版opencv

```
pip3 install opencv-python -i https://pypi.tuna.tsinghua.edu.cn/simple
pip3 install opencv-contrib-python -i https://pypi.tuna.tsinghua.edu.cn/simple
```

##### 10、安装c++版opencv

https://blog.csdn.net/zhaohaowu/article/details/113749936

##### 11、安装ros

https://blog.csdn.net/zhaohaowu/article/details/113749231

##### 12、安装百度网盘

https://pan.baidu.com/download

##### 13、orbslam2运行数据集及电脑相机采集视频流

https://blog.csdn.net/zhaohaowu/article/details/113784886

##### 14、git clone网速慢

方法1：
将github.com更换为github.com.cnpmjs.org
实测只有热点有效
方法2：
首先得用electron-ssr上网

```
git config --global http.proxy 'socks5://127.0.0.1:1080' 
git config --global https.proxy 'socks5://127.0.0.1:1080'
```

实测非常快

##### 15、fail to connect port

env|grep -i proxy 查看代理设置情况，将其逐一unset

```
unset all_proxy && unset ALL_PROXY
unset no_proxy && unset NO_PROXY
unset http_proxy && unset HTTP_PROXY 
unset https_proxy && unset HTTPS_PROXY
```

##### 16、electron-ssr使用

链接: https://pan.baidu.com/s/1IKw_fla0tKGhVYWXlIjS1Q  密码: ok0j
双击安装后要进行自动下载（用于更新），代理那里自动手动都可以，chrome打开就可以用，火狐需要设置

```
sudo apt install proxychains
sudo gedit /etc/proxychains.conf
#注释最后一行添加socks5 127.0.0.1 1080，之后终端就可以科学上网
proxychains wget google.com #验证wget可行
proxychains bash #后面的终端都使用科学上网
proxychains firefox #打开的火狐浏览器可以科学上网
proxychains rosdep update #解决rosdep update问题
```

##### 17、orbslam2生成稠密地图

http://106.15.203.17/

##### 18、安装typora

```
wget -qO - https://typora.io/linux/public-key.asc | sudo apt-key add -
sudo add-apt-repository 'deb https://typora.io/linux ./'
sudo apt-get update
sudo apt-get install typora
```

##### 19、Found unsuitable Qt version "" from NOTFOUND, this code requires Qt 4.x Call Stack

```
sudo apt-get install qt4-default 
```

##### 20、Could NOT find move_base_msgs (missing: move_base_msgs_DIR)

```
sudo apt-get install ros-melodic-navigation
```

##### 21、ERROR: cannot launch node of type [gmapping/slam_gmapping]: gmapping

```
ROS path [0]=/opt/ros/melodic/share/ros
ROS path [1]=/home/zhw/test/src
ROS path [2]=/opt/ros/melodic/share
sudo apt-get install ros-melodic-gmapping
```

##### 22、安装显卡驱动（解决外接显示屏无法使用问题和屏幕亮度无法调节问题）

https://blog.csdn.net/zhaohaowu/article/details/114284288

##### 23、安装cuda10+cudnn7

https://blog.csdn.net/zhaohaowu/article/details/114072620

##### 24、安装rar

```
sudo apt-get install rar unrar
sudo apt-get install rar rar
```

##### 25、安装parcellite

```
sudo apt-get install parcellite
```


使用：ctrl c复制，ctrl alt h选择复制内容，ctrl v粘贴选择内容

##### 26、ERROR: cannot launch node of type [depthimage_to_laserscan/depthimage_to_laserscan]: depthimage_to_laserscan

```
sudo apt install ros-melodic-depthimage-to-laserscan
```

##### 27、解决触摸板无法使用

https://blog.csdn.net/zhaohaowu/article/details/114287116

##### 28、美化

```
sudo apt-get install gnome-tweak-tool
```

##### 29、安装c++版zbar

```
wget http://downloads.sourceforge.net/project/zbar/zbar/0.10/zbar-0.10.tar.gz
tar -zvxf zbar-0.10.tar.gz
export CFLAGS=""
./configure --enable-shared --enable-static --disable-video --without-gtk --without-qt --without-python --without-imagemagick
make
make install
```

##### 30、安装python版zbar

https://pypi.python.org/simple/zbar/
下载zbar-0.10.tar.bz2

```
cd zbar-0.10.tar.bz2
sudo python setup.py install
```

##### 31、安装vscode

https://code.visualstudio.com/
解决vscode安装完空格显示很短
ctrl加逗号，打开设置，搜索font family，将原内容修改为'monospace'
解决无法跳转到函数定义
安装c/c++和拓展插件

##### 32、安装vncviewer

```
sudo apt install tigervnc-viewer 
```


