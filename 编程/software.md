# Mac使用

## 软件

解压：Keka

解压：eZip

播放器：IINA

手势：betterandbetter

分屏：rectangleapp.com

分屏：Magnet

卸载软件：appcleaner

文件格式转换：Permute3

网站视频下载：Downie 4

种子下载：Folx

adobe激活破解：Adobe zii

Mac性能监控：iStat Menus

手机连接mac: HandShaker(有线无线都可)

动态壁纸：backgrounds

## 终端代码

隐藏变灰：defaults write com.apple.Dock showhidden -bool TRUE; killall Dock

任何来源安装：sudo spctl --master-disable

重置主机名：sudo scutil --set HostName 新主机名

查找软件目录：where -a 软件名

## 快速预览文件

选中按空格键

## 触控板手势

#### 隐藏除了某个软件的所有窗口

option+command+鼠标点击保留的软件

#### 关闭当前页面

command + w

#### 隐藏当前程序

command + H

#### 翻译



#### 右键

双指轻按

#### 滚动

双指向上下

#### 放大

双指分开滑动

#### 智能缩放软件

双指双击

#### 缩放MAC屏幕

设置：偏好-辅助功能-缩放

command+双指向上下滑动

#### 旋转

两指顺时针、逆时针滑动

#### 通知中心

两指触控板最右侧左滑出现、两指触控板最右侧右滑隐藏

#### 页面切换（浏览器）

双指左滑、右滑？？？智能滑动页面内容

#### 拖动窗口、选择文字、拖拽文件

三指滑动

#### 切换不同桌面、全屏应用

四指左右滑动

#### 调度中心

四指向上滑动

#### 平铺一个程序的所有界面

四指向下滑动

#### 启动台

拇指与三指合滑动

分开退出启动台

#### 显示桌面

拇指与三指分开滑动

# Windows快捷键

打开资源管理器：`Win+E`

打开任务管理器：`Ctrl+Shift+ESC`

# Win+R

| 功能               | 命令                       |
| ------------------ | -------------------------- |
| 查询计算机名等信息 | systeminfo                 |
| 查询计算机IP等信息 | ipconfig                   |
| ping IP地址        | ping  "IP" -t              |
| 通过IP查找机器名   | nbtstat -A  "IP"           |
| 通过机器名查找IP   | nbtstat -A  "机器名"       |
| 查看BIOS时间       | WMIC BIOS get  releasedate |
| 服务               | services.msc               |
| 卸载软件           | appwiz.cpl                 |
| 控制面板           | control                    |

# DOS

获取IP：`ipconfig /all`

刷新DNS：`ipconfig /flushdns`

查看端口使用情况`netstat -ano`

查看8080端口是否被占用：`netstat -ano|findstr 8080`为空未被使用，有值说明被使用

清空：`cls`

查看安装过的pip：`pip freeze	`

进入D盘：`cd /d d:`

进入文件夹：`cd folder1\folder2`

查找copy的用法： `copy /?`

## 远程连接Linux服务器

```
ssh root@175.24.126.242  回车
问yes/no  输入yes  回车
输入服务器密码
```

## MySQL操作

```
# 连接mysql
mysql -uroot -proot

# 创建数据库
create database flask_sql_demo charset=utf8;

# 进入数据库
use flask_sql_demo

# 查看数据库里的表
show tables;

# 查看某表
desc table1;

# 查询内容
select * from table1

# 删除数据库
drop database flask_sql_demo;

# 退出mysql
exit
```



# Anaconda

## Windows

### 安装

1. https://repo.anaconda.com/archive/ 
2. 下载"Anaconda3-5.2.0-windows-x86 64.exe"

## Mac

### 安装

安装包：https://github.com/conda-forge/miniforge/releases

选择：Miniforge....sh    

下载好是.sh文件

进入中断"bash ***.sh"运行安装

| 功能                   | 命令                                     |
| ---------------------- | ---------------------------------------- |
| 创建环境               | conda create -n 环境名 python=3.8        |
| 查看环境下已有的安装包 | conda list                               |
| 查看所有虚拟环境       | conda info -e                            |
| 激活环境、进入环境     | conda activate 环境名                    |
| 安装包                 | pip install xxxx 或者 conda install xxxx |
| 删除包                 | conda remove xxxx                        |
| 退出当前虚拟环境       | conda deactivate                         |
| 删除环境               | conda remove -n 环境名 --all             |
| 克隆环境               | conda create -n 新环境 --clone 旧环境    |
| 安装本地压缩包         | conda install --use-local xxx.tar.gz     |
| import wx 微信模块     | pip install wxPython                     |
| 查看conda信息，多少位  | conda info                               |
| 切换32位               | set CONDA_FORCE_32BIT=1                  |
| 切换64位               | set CONDA_FORCE_32BIT=0                  |

## 安装包

| 安装什么包       | 命令                                                         |
| ---------------- | ------------------------------------------------------------ |
| OpenCV-Python    | pip install opencv-python                                    |
| OpenCV(训练数据) | pip install opencv-contrib-python                            |
| sklearn          | pip install -U scikit-learn                                  |
| matplotlib       | pip install matplotlib                                       |
| numpy            | conda install numpy                                          |
| pandas           | pip install pandas ???                                       |
| plotly绘图库     | pip install plotly                                           |
| jupyter notebook | conda install jupyter notebook                               |
| mysql            | conda install  mysql-connector-python                        |
| win32con         | pip install pypiwin32<br />import win32con                   |
| win32???         | pip install pywin32 -i https://pypi.tuna.tsinghua.edu.cn/simple |
| 模型部署         | pip install tensorflow-serving-api                           |
| grpc             | pip install grpcio<br />import grpc                          |
| web              | pip install web.py<br />import web                           |
|                  |                                                              |
|                  |                                                              |
|                  |                                                              |
|                  |                                                              |
|                  |                                                              |

| PyQt5                  |                                                              |
| ---------------------- | ------------------------------------------------------------ |
| pyinstaller(pyqt5打包) | pip install pyinstaller                                      |
| pyqt画图               | pip install pyqtgraph                                        |
| pyqt界面美化           | pip install qtawesome                                        |
| pyqt网页页面           | pip install PyQtWebEngine<br />from PyQt5.QtWebEngineWidgets import * |
| pyqt黑界面美化         | pip install qdarkstyle                                       |
| PYQT 数据3D可视化      | pip install PyQtDataVisualization<br />from PyQt5.QtDataVisualization import * |

| flask                                                   |                                                              |
| ------------------------------------------------------- | ------------------------------------------------------------ |
| flask                                                   | pip install flask                                            |
| flask-sqlalchemy<br />python对象操作数据库，不用sql语句 | pip install flask-sqlalchemy<br />from flask_sqlalchemy import SQLAlchemy |
| flask-mysql                                             | pip install flask-mysql                                      |

| Django |                                                   |
| ------ | ------------------------------------------------- |
| Django | install django -i https://pypi.douban.com/simple/ |



# Tensorflow

+ 麻烦，推荐第二种装法

## 安装

1. 更新NVIDIA驱动

2. 安装Visual C++

   https://support.microsoft.com/zh-cn/help/2977003/the-latest-supported-visual-c-downloads

3. 安装CUDA(10.0、windows、local、x86 64）

   1）下载：https://developer.nvidia.com/cuda-10.0-download-archive?target_os=Windows&target_arch=x86_64&target_version=10&target_type=exelocal

   2）安装：

   1. 点开"CUDA"选项

      ​	取消勾选"Visual Studio Integration"

   2. 点开"Driver components"

      ​	Display Driver。如果后一个版本号>前一个版本号，去掉勾选。反之勾上

   3. 检验：

      ​	● C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.0\bin

      ​		如果安装目录下bin文件夹下有"nvcc.exe"说明成功

      ​	● C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.0\extras\CUPTI\libx64

      ​		如果目录中有状态库"cupti64_100.dll"说明成功

1. cuDNN：

   1. 下载：https://developer.nvidia.com/rdp/cudnn-download
   2. 选择"Download cuDNN v7.6.5 (November 5th, 2019), for CUDA 10.0"
   3. 选择"cuDNN Library for Windows 10"进行下载
   4. 解压，将cuda文件夹改名为"cudnn"
   5. 将cudnn文件夹复制到"C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.0\"目录下
   6. 确认目录"C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.0\cudnn\bin"下文件"cudnn64_7.dll"存在

2. 配置环境变量：

   1. 电脑--属性--高级系统设置--环境变量

   2. 选中"系统变量"下的"Path"进行编辑，添加下面三个路径

      ```
      C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.0\cudnn\bin
      C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.0\libnvvp
      C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.0\extras\CUPTI\libx64
      C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.0\cudnn\bin
      ```

   3. 将上面4个路径按顺序置顶，保存

3. 在conda环境中安装numpy包

   ```
   conda install numpy
   ```

4. 打开Pycharm--File--Settings--Project:PythonProject--Python Interpreter

   1. 将conda的tensorflow环境下python.exe添加到Python INterpreter中
   2. 点击"+"号，输入"tensorflow-gpu"，选中，点击"Install Package"

   ```
   pip install tensorflow-gpu -i https://mirrors.aliyun.com/pypi/simple
   或
   pip install tensorflow-gpu==2.3.0 -i https://pypi.douban.com/simple/
   ```

### cpu版tensorflow去除警告

```
import os
os.environ['TF_CPP_MIN_LOG_LEVEL']='2'
```

## 命令

```
import tensorflow as tf
```

# Tensorflow第二种装法

成功

```
RTX2060
conda create -n tensorflow python=3.7
conda install cudatoolkit=10.1
conda install cudnn=7.6.5
pip install tensorflow-gpu==2.3.0 -i https://pypi.douban.com/simple/
```



# Pycharm

## 下载

https://www.jetbrains.com/zh-cn/pycharm/download/#section=windows

## 更改快捷键

File-setting-Keymap-Editor Actions

+ 更改方向键

```
up => Alt+i
down => Alt+k
left => Alt+j
right => Alt+l

```

+ 放大缩小字体

  右键"Add Mouse Shortcut "

```
Increase Font Size => Ctrl + Wheel down
Decrease Font Size => Ctrl + Wheel up
```

+ 更改跳转下一行（可考虑）

```
shift+回车 => alt + 回车
```



## 快捷键

| 功能         | 快捷键                 |
| ------------ | ---------------------- |
| 查看代码定义 | Ctrl+B                 |
| 同时修改多行 | 鼠标中键拖动           |
| 查看注释     | 按住Ctrl，光标放在上面 |
| 格式代码     | 选中ctrl+alt+L         |
| 向下插入     | shift+enter            |
| 向上插入     | ctrl+alt+enter         |
| 光标         | end                    |
|              |                        |
|              |                        |
|              |                        |

# Pytorch???

1. 1. 安装anaconda(查看GPU算力Geforce RTX2060 7.5)，安装后配置环境

      1. https://repo.anaconda.com/archive/ 

         （anaconda下载地址）

         ```
         //成功选项
         Anaconda3-5.2.0-windows-x86 64.exe
         
         ```

      //成功选项
         详见网址
      https://blog.csdn.net/ziqingnian/article/details/109099682

         ```
      
         ```

   2. 进入“Anaconda Prompt”，输入“python”回车查看版本,比如3.8.5版本。

   3. 输入“conda create -n pytorch python=3.8”,回车创建pytorch环境用来安装pytorch。输入“y”确定安装

   4. 输入“conda activate pytorch”进入环境。

   5. 输入“pip list”,查看是否有pytorch.没有则进行下一步。

   6. 进入“https://pytorch.org”，选择自己的安装配置（打开NVIDIA控制面板，点击 帮助——系统信息——组件，可以看到cuda支持版本，可兼容低版本cuda），复制安装命令。如：“conda install pytorch torchvision torchaudio cudatoolkit=10.2 -c pytorch”

   7. 在“Anaconda Prompt”窗口，pytorch环境下，黏贴上一步命令回车，输入"y"，安装。（如果安装过慢，考虑离线安装pytorch包和cudatoolkit包）(或者考虑清华源安装)

      ```
      //成功选项
      详见网址
      https://blog.csdn.net/ziqingnian/article/details/109099682
      ```

      ==清华源下载==https://mirrors.tuna.tsinghua.edu.cn/anaconda/archive/

2. 安装后，在pytorch下输入“pip list”,查看是否有“torch”，有则进行下一步

3. 在pytorch环境下，输入“python”回车，再输入“import torch”

   4. 输入“torch.cuda.is_available()”，返回Ture则说明支持GPY

4. 安装Jupyter

   1. 在pytorch环境下，输入“conda install nb_conda”回车
   2. 输入“y”回车
   3. 安装完后输入“jupyter notebook”回车
   4. 在弹出网页右上角选择“New”,选择“Python [conda env:pytorch]”
   5. 弹出网页中“输入import torch”，按“shift+回车”（运行且跳转到下个代码块）

5. pycharm：setting-python interpreter,设置为C:\Users\zhonghua.deng\Anaconda3\python.exe

   1. https://www.jetbrains.com/zh-cn/pycharm/download/#section=windows （pycharm下载地址）

   2. tensorflow

# Pytorch

https://blog.csdn.net/ziqingnian/article/details/109099682

```

conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge 
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/msys2/
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/pytorch/
conda install pytorch torchvision torchaudio cudatoolkit=10.2
```

```
conda config --set remote_read_timeout_secs 1000.0

修改延时（conda 下载久了，会自动断开），800不行设置1000,1000不行设置1200进行尝试
```



# jupyter

1. anaconda进入对应的环境

2. 安装

   ```
   conda install jupyter notebook
   ```

3. 进入到使用jupyter的文件夹

   ```
   cd /d D:\Projects\PythonProject\Demo_Tkinter
   ```

4. 进入对应conda环境，运行jupyter

   ```
   jupyter notebook
   ```

   

### jupyter智能提示，补全代码

1. 关闭jupyter

2. 进入conda的对应环境

3. 安装

   ```
   pip install jupyter_contrib_nbextensions
   jupyter contrib nbextension install --user
   ```

4. 安装

   ```
   pip install --user jupyter_nbextensions_configurator
   juyter contrib nbextension install --user --skip-running-check
   ```

5. 进入对应环境，运行jupyter

6. jupyter菜单栏会出现“N bextensions”,点击

7. 勾选“Hinterland”

8. 重启jupyter

### 快捷键

| 功能               | 快捷键      |
| ------------------ | ----------- |
| 运行，跳转下单元   | shift+enter |
| 运行，不跳转下单元 | Ctrl+enter  |
| 命令模式           | ESC         |
| 上方添加cell       | A           |
| 下方添加cell       | B           |
| 删除当前cell       | 双击D       |
|                    |             |

# LabelImg

### 教程：

python5里卷积-第五节-08

### 网址

https://github.com/tzutalin/labelImg

### 安装

1. 打开Anaconda Prompt，进入相应环境

2. cd到labelImg解压目录

3. 执行下面代码

4. ```
   conda install pyqt=5
   conda install -c anaconda lxml
   pyrcc5 -o libs/resources.py resources.qrc
   python labelImg.py
   python labelImg.py [IMAGE_PATH] [PRE-DEFINED CLASS FILE]
   ```

### 快捷键Hotkeys

| Ctrl + u         | Load all of the images from a directory   |
| ---------------- | ----------------------------------------- |
| Ctrl + r         | Change the default annotation target dir  |
| Ctrl + s         | Save                                      |
| Ctrl + d         | Copy the current label and rect box       |
| Ctrl + Shift + d | Delete the current image                  |
| Space            | Flag the current image as verified        |
| w                | Create a rect box                         |
| d                | Next image                                |
| a                | Previous image                            |
| del              | Delete the selected rect box              |
| Ctrl++           | Zoom in                                   |
| Ctrl--           | Zoom out                                  |
| ↑→↓←             | Keyboard arrows to move selected rect box |

# VScode

### 设置

##### 自动格式化代码

文件=>首选项=>设置

输入emmet.include

用户中点击setting.json

{}中加入

"editor.formatOnType":true,

 "editor.formatOnSave":true

保存

![image-20201005124451293](markdownImg/software/image-20201005124451293.png)

注意：千万不要装prettier

### 插件

Chinese (Simplified) Language Pack for Visual Studio Code

Open in browser

Auto rename tag

小程序开发插件：小程序开发助手、minapp、vetur、小程序助手、easy less（重启）

![image-20201016221215060](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20201016221215060.png)

| 换到下一行           | Ctrl+Enter                    |
| -------------------- | ----------------------------- |
| 到下个代码名         | Ctrl+→                        |
| 将行上下移动         | Alt+↑或↓                      |
| 代码行缩进           | Ctrl+【， Ctrl+】             |
| 折叠打开代码块       | Ctrl+Shift+【， Ctrl+Shift+】 |
| 代码格式化           | Shift+Alt+F                   |
| 向上向下复制一行     | Shift+Alt+↑，Shift+Alt+↓      |
| 在当前行下方插入一行 | Ctrl+Enter                    |
| 在当前行上方插入一行 | Ctrl+Shift+Enter              |
| 移动到行尾           | End                           |
| 移动到文件结尾       | Ctrl+End                      |
| 移动到行开头         | Home                          |
| 移动到文件开头       | Ctrl+Home                     |
| 选中当前行           | Ctrl+L                        |
| 选择从光标到行尾     | Shift+End                     |
| 选择从行首到光标处   | Shift+Home                    |
| 选中所有匹配         | Ctrl+Shift+L                  |
| 选中匹配             | Ctrl+D                        |
| 光标回退             | Ctrl+U                        |
|                      |                               |



分屏：点击窗口右上角分屏图标

快捷CDD: CSS Tree

```
选中所有html或者WXML中需要加样式的标签
按Ctrl+Shift+P,调出弹窗，输入css tree，点击
复制所有内容，关闭，不保存
黏贴到less文件中对应位置，并Ctrl+D选中所有比如view，删除
```

# PYQT5

## 1. 安装

1. 进入ananconda对应环境

```
pip install sip    //这个是pyqt开发商提供的支持包

pip install pyqt5 

pip install pyqt5-tools

# pycharm对pyqt输入进行提示
pip install pyqt5-stubs

#图形、图标绘制包
pip install pyqtgraph

# pyqt界面美化
pip install qtawesome

# 黑界面美化
pip install qdarkstyle

# 网页页面加载
pip install PyQtWebEngine
(from PyQt5.QtWebEngineWidgets import *)

# PYQT 数据3D可视化
pip install PyQtDataVisualization
（from PyQt5.QtDataVisualization import *）
```

## 2. 添加PYQT工具

#### 配置打开PYQT工具

pycharm-settings-tools-External Tools-添加

+ name: `QT Designer`

+ Program:找到pyqt5在annaconda安装环境下的designer.exe

  `C:\Users\zhonghua.deng\Anaconda3\envs\model\Lib\site-packages\qt5_applications\Qt\bin\designer.exe`

+ Working directory：`$FileDir$`

#### 配置.ui转.py工具

pycharm-settings-tools-External Tools-添加

+ name: `PyUIC`

+ Program:找到pyqt5在annaconda安装环境下的pyuic5.exe

  `C:\Users\zhonghua.deng\Anaconda3\envs\model\Scripts\pyuic5.exe`

+ Argument: `$FileName$ -o $FileNameWithoutExtension$.py`

+ Working directory：`$FileDir$`

### 配置.qrc转_rc.py工具

pycharm-settings-tools-External Tools-添加

+ name: `Pyrcc`

+ Program:找到pyqt5在annaconda安装环境下的pyuic5.exe

  `C:\Users\zhonghua.deng\Anaconda3\envs\model\Scripts\pyrcc5.exe`

+ Argument: `$FileName$ -o $FileNameWithoutExtension$_rc.py`

+ Working directory：`$FileDir$`

## 3. 使用

+ 另创建一个.py文件

```
import sys
import test  # ui转为py的文件名
from PyQt5.QtWidgets import QApplication, QMainWindow

if __name__ == '__main__':
    app = QApplication(sys.argv)
    MainWindow = QMainWindow()
    ui = test.Ui_Dialog()
    ui.setupUi(MainWindow)
    MainWindow.show()
    sys.exit(app.exec_())
```

# MySQL(Workbench)

### 工具

Workbench

### 创建数据库

1. 打开"workbench"
2. 点击工具栏图标"Create a new Schema in the connected server"
3. 输入name
4. "Charset/Collation":选"uft8"

### 新建表格

1. 打开"workbench"
2. 右击table选择"Create table"
3. 输入name
4. "Charset/Collation":选"uft8"
5. 选择主键PIC，是否为空NN，自增AI

# AutoCAD

### 安装包

百度磁盘-软件

### 快捷键

| 功能 | 快捷键 |
| ---- | ------ |
|      |        |
|      |        |
|      |        |

# Postman

1. 下载地址：https://www.postman.com/downloads/
2. 安装
3. 中文包下载地址：https://gitee.com/hlmd/PostmanCn/releases
4. app.zip解压后，将文件夹app复制到Postman安装目录中文件夹Resources下

# 腾讯云服务器

1. 购买Linux服务器，选centOS7系统
2. 进入"示例"，修改root密码
3. 进入"安全组"，"新建"-"放通22，80，443，3389端口和ICMP协议"-"确定"
4. "修改规则"-"添加规则"
   + 来源：0.0.0.0/0，协议端口：TCP:8888（作为宝塔面板连接端口）
   + 保存
5. 进入"示例"-"更多"-"安全组"-"配置安全组"-勾选刚刚新建的安全组，确定
6. 下载XSHELL并安装，用XSHELL连接服务器
7. 进入宝塔官网，linux，点击"立即安装"
8. 复制"Linux面板7.5.2安装命令"，到XSHELL中黏贴，回车安装，全部选y
9. 安装完后输入"5"，更改密码
10. '"6",修改用户名
11. "14",查看面板连接，复制链接，浏览器粘贴
12. 输入账号、密码登陆
13. 弹窗选择"推荐一键安装"
14. "数据库"-"添加数据库"-修改账号、密码-确定

# Fusion360

### 教程

https://www.bilibili.com/video/BV14t411d76X

### 快捷键

| 功能             | 快捷键       |
| ---------------- | ------------ |
| 平移             | 按住鼠标滚轮 |
| 旋转             | Shift+按滚轮 |
| 细分曲面模式切换 | Alt+1,2,3    |
