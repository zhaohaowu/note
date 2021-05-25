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
git config --global --unset http.proxy
git config --global --unset https.proxy
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

https://cloud.189.cn/t/MRzaYzEJbQbm
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

##### 32、安装vncviewer和remmina

```
sudo apt install tigervnc-viewer 
```

```
sudo apt-add-repository ppa:remmina-ppa-team/remmina-next
sudo apt update
sudo apt install remmina remmina-plugin-rdp remmina-plugin-secret
```

##### 33、安装zed2，astra和kinect相机

```
cd ~/catkin_ws/src/ 
git clone https://github.com/stereolabs/zed-ros-wrapper.git
cd ~/catkin_ws
catkin_make -DCMAKE_BUILD_TYPE=Release
echo source $(pwd)/devel/setup.bash >> ~/.bashrc
source ~/.bashrc
roslaunch zed_wrapper zed.launch
```

```
cd ~/catkin_ws/src
git clone https://github.com/orbbec/ros_astra_camera
roscd astra_camera
./scripts/create_udev_rules
cd ~/catkin_ws
catkin_make --pkg astra_camera
roslaunch astra_camera astra.launch
```

```
sudo apt-get install ros-melodic-freenect-*
git clone https://github.com/avin2/SensorKinect.git
sudo ./install.sh 
roslaunch mrobot_bringup freenect.launch 
```

##### 33、安装cartographer

https://google-cartographer-ros.readthedocs.io/en/latest/compilation.html

##### 34、安装aruco

https://sourceforge.net/projects/aruco/files/?source=navbar

cd aruco-3.1.2&&mkdir build&&cd build&&cmake ..&&sudo make install

##### 35、安装evo

```
git clone https://github.com/MichaelGrupp/evo
cd evo
pip install --editable . --upgrade --no-binary evo
测试
cd test/data
evo_traj kitti KITTI_00_ORB.txt KITTI_00_SPTAM.txt --ref=KITTI_00_gt.txt -p --plot_mode=xz
然后出现ModuleNotFoundError: No module named 'tkinter'
sudo apt-get install python3-tk
```

##### 36、安装sophus

```
git clone https://github.com/strasdat/Sophus.git
cd Sophus && mkdir build && cd build && cmake .. && sudo make install
```

##### 37、安装pangolin

```
sudo apt-get install libglew-dev
sudo apt-get install libboost-dev libboost-thread-dev libboost-filesystem-dev
sudo apt-get install libpython2.7-dev
git clone https://github.com.cnpmjs.org/stevenlovegrove/Pangolin.git
cd Pangolin && mkdir build && cd build && cmake .. && cmake --build . && sudo make install
```

##### 38、安装ceres

```
sudo apt-get install liblapack-dev libsuitesparse-dev libcxsparse3 libgflags-dev libgoogle-glog-dev libgtest-dev
git clone https://github.com/ceres-solver/ceres-solver
cd ceres-solver && mkdir build && cd build && cmake .. && make  && sudo make install
```

##### 39、安装g2o

```
sudo apt install qt5-qmake qt5-default libqglviewer-dev-qt5 libsuitesparse-dev libcxsparse3 libcholmod3
cd g2o && mkdir build && cd build && cmake .. && make  && sudo make install
```

##### 35、slam14讲笔记

第三章

1、任意向量对应一个反对称矩阵

a^=[0 -a3 a2;

​     a3 0 -a1;

​    -a2 a1 0]

2、旋转矩阵R，旋转向量θ*n，欧拉角，四元数

θ=arccos((tr(R)-1)/2)

n为R特征值1对应的特征向量

偏航角yaw绕z轴旋转，俯仰角pitch绕y轴旋转，横滚角roll绕x轴旋转

3、Matrix3d定义旋转矩阵，AngleAxisd定义旋转向量，Vector3d定义欧拉角，Quaterniond定义四元数

旋转向量转旋转矩阵，旋转向量.matrix()和旋转向量.toRotationMatrix()

旋转矩阵转欧拉角，旋转矩阵.eulerAngles(2,1,0)

旋转向量转四元数，Quaterniond(旋转向量)

旋转矩阵转四元数，Quaterniond(旋转矩阵)

第四章

1、李群有两个，SO(3)和SE(3)，分别是旋转矩阵R和变换矩阵T

李代数对应的so(3)和se(3)，分别是φ和ξ，R=exp(φ^)，T=exp(ξ^)，ξ=[ρ，φ]

SO(3)的李代数求导，δ(Rp)/δφ=-(Rp)^

SE(3)的李代数求导，δ(Tp)/δδξ=[I -(Rp+t)^;0 0]

2、sophus里面

定义李群：

Sophus::SO3d SO3_R(旋转矩阵); 

Sophus::SE3d SE3_Rt(旋转矩阵，平移向量);

定义李代数：

Vector3d so3 = SO3_R.log();

Vector6d se3 = SE3_Rt.log();

3、绝对轨迹误差ATE和相对位姿误差RPE

ATE：

double error, rmse;

for(int i=0; i<estimated.size(); i++){

Sophus::SE3d p1=estimated[i], p2=groundtruth[i];

error=(p2.inverse()*p1).log().norm();

rmse+=error*error;

}

rmse=sqrt(rmse/double(estimated.size()));

第五章

1、针孔相机模型
$$
ZP_{uv}=Z\begin{bmatrix}u\\ v\\1 \end{bmatrix}=\begin{bmatrix}f_x&0&c_x\\0&f_y&c_y\\0&0&1 \end{bmatrix}\begin{bmatrix}X\\Y\\Z\end{bmatrix}=KP_c=K(RP_w+t)
$$
2、双目相机深度z=fb/d，f为焦距，b为基线，d为视差，视差通过GPU或FPGA实时计算

3、RGBD相机通过红外结构光和飞行时间求像素深度

第六章

1、
$$
e_1=x_k-f(x_{k-1},u_k)\\
e_2=z_{k,j}-h(x_k,y_j)\\
min(J(x,y))=\sum_ke_1^TR_k^{-1}e_1+\sum_k\sum_je_2^TQ_{k,j}^{-1}e_2
$$
2、非线性最小二乘

- $minF(x)=\frac 12||f(x)||_2^2$

- 给定初始值$x_0$

- 第k次迭代，寻找增量$x_k$，使得$||f(x_k+△x_k)_2^2||$达到极小值

- 若$△x_k$足够小，停止迭代

- 否则，令$x_{k+1}=x_k+△x_k$，返回第二步

3、求△x的几种方法

- 最速下降法：$△x=-J$，过于贪心，容易走出锯齿路线，反而增加迭代次数

- 牛顿法：$H△x=-J$，计算目标函数海塞矩阵，大规模问题较难计算

- 高斯牛顿法：$JJ^T△x=-Jf(x)$，避免二阶求导，但$JJ^T$只有半正定性，可能为奇异矩阵或病态矩阵

- 列文伯格-马夸尔特法：$(JJ^T+\lambda I)△x=-Jf(x)$，将高斯牛顿法引入阻尼项，避免奇异和病态，但收敛速度慢

4、ceres库和g2o库使用

第七章

1、提取ORB特征

- FAST角点提取，角点为像素灰度变化明显的地方，构件图像金字塔，提取不同层图像角点，特征点方向定义为几何中心指向质心
- BRIEF描述子，对特征点周围图像进行描述，使用前面计算的特征点的方向

2、特征匹配

- 求当前帧图像的特征点与下一帧图像的每个特征点的描述子的汉明距离，取最小值作为匹配点

3、2D-2D 对极几何

- $s_1p_1=KP，s_2p_2=K(RP+t)$
- 我们假设$x_1$和$x_2$为$p_1$和$p_2$在归一化平面的坐标，即$x_1=K^{-1}p_1，x_2=K^{-1}p_2$
- $s_2K^{-1}p_2=s_1RK^{-1}p_1+t$，即$s_2x_2=s_1Rx_1+t$
- 两边左乘$x_2^Tt$^，左侧为零
- $p_2^TK^{-T}t$^$RK^{-1}p_1=0$ ，即$x_2^Tt$^$Rx_1=0$
- 根据像素点$p_1，p_2$和相机内参K用八点法求E=t^R
- 根据E奇异值分解求R和t
- 本质矩阵E=t^R，基础矩阵F=$K^{-T}$t^R$K^{-1}$，单应矩阵H（假设特征点位于同一平面上）
- 求出的t，其尺度不确定，将t归一化，此时t的单位为1，初始时，使机器人运动一段距离，即初始化的两张图像的平移，以此距离为t的单位，被称为单目slam初始化
- 通过本质矩阵E求R和t时，相机不能只有旋转，否则E为0，无法求解R

4、三角测量

- $s_2K^{-1}p_2=s_1RK^{-1}p_1+t$，即$s_2x_2=s_1Rx_1+t$
- 两边左乘$x_2$^，可求$s_2$
- 代码中，`cv::triangulatePoints`函数接受的参数是两个相机位姿和特征点在两个相机坐标系下的坐标，输出三角化后的特征点的3D世界坐标
- 此时的pts_4d为齐次坐标，将其转换为其次坐标，为每一个数都除以第4个元素，然后取出前3个元素

5、3D-2D PnP

- 
