# Docker-Flask
这是一个关于 如何实现简单flask http环境，并将其放置在docker容器中执行的学习项目

关于docker安装：
参考https://www.runoob.com/docker/centos-docker-install.html
如果当中遇到linux内核版本过低，参考https://www.jianshu.com/p/5498286c0372
以下命令为内核版本过低的执行命令
yum install --setopt=obsoletes=0 \
   docker-ce-17.03.2.ce-1.el7.centos.x86_64 \
   docker-ce-selinux-17.03.2.ce-1.el7.centos.noarch # on a new system with yum repo defined, forcing older version and ignoring obsoletes introduced by 17.06.0

启动docker: sudo systemctl start docker

关于启动：
下载docker文件夹，将其放置linux环境运行
进入 ../docker 目录下 
1、编译当前目录下的Dockerfile，将其命名为一个叫flask的镜像
命令：sudo docker build -t flask .

编译过程中可能时间较长（下载云镜像）

2、启动docker容器
命令：sudo docker run -it -d -p 5000:5000/tcp flask 

其中 flask 启动命令 和 /bin/bash命令在 doflask.sh 脚本中
-p 端口 5000对应5000 

3.打开web页面访问linux本机所在的 ${ip}:5000
