# 教程



# 安装、加速、卸载

### 安装

```shell
# 卸载
yum remove docker \
                  docker-client \
                  docker-client-latest \
                  docker-common \
                  docker-latest \
                  docker-latest-logrotate \
                  docker-logrotate \
                  docker-engine

# 需要的安装包
yum install -y yum-utils

# 设置镜像的仓库
yum-config-manager \
    --add-repo \
    http://mirrors.aliyun.com/docker-ce/linux/centos/docker-ce.repo

# 更新yum软件包索引
yum makecache fast

# 安装docker  ce社区版
yum install docker-ce docker-ce-cli containerd.io

# 启动docker
systemctl start docker

# 查看docker版本信息,判断是否安装成功
docker version


# 启动hello world镜像进行测试
docker run hello-world

# 查看下载的hello-world镜像
docker images

#docker 默认工作路径
/var/lib/docker
```

### 镜像加速

阿里云镜像加速地址：https://cr.console.aliyun.com/cn-hangzhou/instances/mirrors

```shell
# 1
sudo mkdir -p /etc/docker

sudo tee /etc/docker/daemon.json <<-'EOF'
{
  "registry-mirrors": ["https://lo1rtoq6.mirror.aliyuncs.com"]
}
EOF

sudo systemctl daemon-reload

sudo systemctl restart docker
```

### 卸载

```shell
# 卸载依赖
yum remove docker-ce docker-ce-cli containerd.io
# 删除资源
rm -rf /var/lib/docker
```



# 命令

```shell
-a  只显示镜像id
-q	显示所有镜像
-f	强制
```

```shell
port  	  # 查看映射端口对应的容器内部源端口
pause	  # 暂停容器
ps        # 猎户容器列表
pull      # 从docker镜像源服务器拉取指定镜像或者库镜像
push      # 推送指定镜像或者库镜像至docker源服务器
restart   # 重启运行的容器
rm        # 移除一个或多个容器
rmi       # 移除一个或多个镜像 （无容器使用该镜像才可删除，否则需要删除相关容器才可继续或 -f 强制删除）
run       # 创建一个新的容器并运行一个命令
save      # 保存一个镜像为一个 tar 包【对应 load】
search    # 在 docker hub 中搜索镜像
start     # 启动容器
stop      # 停止容器
tag       # 给源中镜像打标签
top       # 查看容器中运行的进程信息
unpause   # 取消暂停容器
version   # 查看 docker版本号
wait      # 截取容器停止时的退出状态值
```

| centOS7命令                              |                                               |
| ---------------------------------------- | --------------------------------------------- |
| 开启/关闭                                | service docker start/stop                     |
|                                          |                                               |
|                                          |                                               |
| 查看所有命令                             | docker --help                                 |
| 查看某个命令使用方式                     | docker images --help                          |
| 查看docker系统信息，有多少个镜像、容器等 | docker info                                   |
| 开启容器                                 | docker run -d -p 80:80 docker/getting-started |
| 解压                                     | tar -zxvf nginx-1.18.0.tar.gz                 |

| 镜像命令 |                                                              |
| -------- | ------------------------------------------------------------ |
| 查看镜像 | docker images<br />docker images -a 显示所有镜像<br />docker images -q 只显示镜像ID<br />docker images -aq 显示所有镜像ID |
| 搜索镜像 | docker search mysql                                          |
| 下载镜像 | docker pull mysql<br />docker pull mysql[:tag]  #tag为指定版本，不加则下载最新<br />比如docker pull mysql:5.7 |
| 删除镜像 | docker rmi<br />docker rmi -f 镜像ID   # 删除某个镜像所有东西<br />docker rmi -f $(docker images -aq)  # 完全删除所有镜像 |

| 容器命令             |                                                              |
| -------------------- | ------------------------------------------------------------ |
| 下载容器             | docker pull centos                                           |
| 新建容器并启动       | docker run [可选参数] image<br />--name="name" 给容器取别名<br />-d  后台方式运行  docker run -d centos<br />-it  交互方式运行，进入容器查看内容<br />-p  指定容器的端口<br />                       主机端口：容器端口。如8080:0880<br />                       ip:主机端口：容器端口<br />                       容器端口<br />  -P  随机指定端口<br /><br />举例：docker run -it centos /bin/bash |
| 启动容器             | docker start 容器id                                          |
| 重启容器             | docker restart 容器id                                        |
| 停止容器             | docker stop 容器id                                           |
| 强制停止当前容器     | docker kill 容器id                                           |
| 退出容器(容器停止)   | exit                                                         |
| 退出容器(容器不停止) | Ctrl+P+D                                                     |
| 列出所有运行的容器   | docker ps<br />docker ps -a 列出正在和曾经运行的容器<br />docker ps -a -n=1  列出最近创建的(几个)容器 |
| 删除容器             | docker rm 容器id<br />docker rm -f 容器id   强制删除某个容器（容器正在运行）<br />docker rm -f $(docker ps -aq)     删除所有容器<br />docker ps -a -q\|xargs docker rm  删除所有容器 |
|                      |                                                              |

| 其他命令                             |                                                              |
| ------------------------------------ | ------------------------------------------------------------ |
| 显示日志                             | docker logs -tf --tail 10 容器id <br /> #显示10条日志，10不加则显示所有日志 |
| 查看容器中的进程信息                 | docker top 容器id                                            |
| 查看镜像的元数据                     | docker inspect 容器id                                        |
| 进入当前正在运行的容器               | docker exec -it 容器id /bin/bash                             |
| 进入容器开始一个新终端，在里面操作   | docker exec                                                  |
| 进入容器正在之心的终端，不启动新进程 | docker attach                                                |
| 从容器内拷贝文件到主机上             | docker cp 容器id:容器内路径 目的主机路径                     |

# docker帮助文档

https://docs.docker.com/engine/reference/commandline/docker/

# 加压缩文件

```shell
# 解压缩
tar -zxvf nginx-1.18.0.tar.gz

# 进入文件夹
cd nginx-1.18.0.tar.gz

# 执行文件
./configure
```



# 案例：docker安装nginx

```shell
# 搜索镜像
docker search nginx

# 下载镜像
docker pull nginx

# 启动服务
# --name 命名
# -p 映射端口
docker run -d --name nginx01 -p 3344:80 nginx

# 进入nginx01
docker exec -it nginx01 /bin/bash

# 查找nginx路径
whereis nginx

# 退出
exit

# 查看nginx01的容器id
docker ps

# 停止nginx01
docker stop 容器id
```

# DockerFile

1. 指令必须是大写字母
2. 从下倒下

### 指令

```shell
FROM			# 基础镜像，如python,centos 
MAINTAINER		# 镜像作者，留姓名+邮箱 DZH<123456@qq.com>
RUN				# 镜像构建的时候需要运行的命令
ADD				# 步骤：tomcat镜像，这个压缩包。添加内容
ENV MYPATH /usr/local	# 创建键值对，方便下面$调用(我觉得没必要)
WORKDIR	$MYPATH	# 镜像的工作目录
VOLUME			# 挂载的目录			
EXPOSE			# 暴露的端口
CMD				# 指定这个容器启动的时候要运行的命令,只有最后一个会生效，可被替代
ENTRYPOINT		# 指定这个容器启动的时候要运行的命令，可以追加命令
ONBUILD			# 当构建一个被继承DockerFile这个时候会运行ONBUILD指令
COPY			# 类似ADD,将我们文件拷贝到镜像中
ENV				# 构建的时候设置环境变量
```

###  创建DockerFile

```shell
# 进入创建mydockerfile的目录
cd ......

# 创建并进入mydockerfile
vim mydockerfile 

# 编写内容
FROM ......

# 保存
wq 回车 

# 查看编写内容
cat mydockerfile

# 构建镜像 -t是target名:版本号
docker build -f mydockerfile -t myimage:0.1 .

# 运行，一定要带版本号
docker run -it myimage:0.1
```



