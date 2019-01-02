#docker命令
## 1. docker image 操作命令
1. sudo docker image ls  (or) docker images               **查看系统所有image**
2. sudo docker pull ubuntu:14.04         				**安装 ubuntu 14.04 image**
	- sudo docker pull bitnami/wordpress    				**安装bitnami的wordpress image**
3. docker image rm [image ID]  (or) docker rmi [image ID] **删除image**

## 2. Dockerfile 编译
3. docker image build (or) docker build       # **将Dockerfile 编译成 image**
4. docker build -t xiaopeng163/hello-world .  			**在当前目录编译Dockerfile**
5. docker history [image_ID]                            **查看image生成过程**

## 3. 容器管理
6. docker run xiaopeng163/hello-world     				**docker运行image**
	- docker run -it ubuntu       							 **交互式运行ubuntu container**
	- docker run -it [image] /bin/bash                  **表示进入containe的 shell中**
	- docker run -d [image]                              **后台运行**
	- docker run -d --name=demo laosuaidami/flask-hello-world  **指定容器名字**
7. docker container ls                   				**当前本地正在运行的程序**
8. docker container ls -a  or docker ps -a              **所有的容器，包括正在运行的，和已经退出的**
9. docker container rm [container_ID]  (or)  docker rm [container_ID]   **删除容器，包括正在运行的，和已经退出的**
10. docker container ls -aq (or) docker container ls -a|awk{'print$1'}
11. docker rm $(docker container ls -aq)     **删除所有container**
12. docker rm $(docker container ls -f 'status=exited' -q)    **删除已经结束的container**
13. docker container commit (or) docker commit  **修改container后变成新的container**
	- docker commit [OPTIONS] CONTAINER [REPOSITORY[:TAG]]
    - eg：docker commit quirky_chatelet hewei/centos-vim-f
14. docker exec -it [container id] [要执行的命令]
	- docker exec -it 05554595249d /bin/bash
	- docker exec -it 05554595249d python
	- docker exec -it 05554595249d ip a     **打印运行的容器IP地址**
15. docker stop/start [container id (or) container name]  **停止容器**
16. docker inspect [container id (or) container name]  **查看容器信息**
16. docker logs [container id (or) container name]  **查看容器日志**	

## 4. [查看官方命令文档 ](https://docs.docker.com/engine/reference/commandline/container/)   
	https://docs.docker.com/engine/reference/commandline/container/

## 4. docker hub 操作
15. docker login / docker logout  **登录退出docker hub**
16. docker push  laosuaidami/hello-world:latest  **将docker推送到docker hub**

# Dockerfile 语法
## FROM
	FROM scratch   # 使用base image
	FROM centos    # 使用base image
	FROM ubuntu:14.04 
	尽量使用官方的image作为base image
	
## LABEL
	LABEL maintainer="xiaoquwl@gmail.com"
	LABEL version="1.0"
	LABEL description="This is description"
	类似代码注释
	
## RUN 
	RUN yum update && yum install -y vim \
	python-dev  # 反斜线换行

	RUN apt-get update && apt-get instll -y perl\
	pwgen --no-install-recommends && rm -rf \
	/var/lib/apt/lists/*   # 注意清理cache
	
	RUN /bin/bash -c 'source $HOME/.bashrc; echo $HOME'

## WORKDIR
	WORKDIR /root
	WORKDIR /test    # 如果没有会自动创建test目录
	WORKDIR demo
	RUN pwd          # 输出结果应该是 /test/demo
	
	使用WORKDIR, 不要用  RUN cd! 尽量使用绝对目录！
	
## ADD and COPY
	ADD hello /
	ADD test.tar.gz /   # 添加的根目录并解压
	
	WORKDIR /root
	ADD hello test/   # root/test/hello
	
	WORKDIR /root
	COPY hello test/
	
	大部分情况， COPY 优于 ADD
	ADD 除了 COPY 还有额外功能（解压）！
	添加远程文件/目录请使用curl或者wget !
	
## ENV
	ENV MYSQL_VERSION 5.6  # 设置常量
	RUN apt-get install -y mysql-server="${MYSQL_VERSION}" && rm -rf /var/lib/apt/lists/*  # 引用常量
	尽量使用，增加可维护性
	
## VOLUME and EXPOSE  （存储和网络）
	
	
## CMD and ENTRYPOINT 
	RUM: 执行命令并创建新的Image Layer
	CMD: 设置容器启动后默认执行的命令和参数
	ENTRYPOINT: 设置容器启动时执行的命令
	
	eg:
	ENTRYPOINT ["/usr/bin/stress"]    这是执行的命令
	CMD ['--verbose']                 这是执行的参数 可以外部输入 也可以设置默认 参数


# 容器的资源限制
## 1. 限制内存	 --memory=xxxM    
	docker run --memory=200M laosuaidami/docker-stress --vm 1 --verbose --vm-bytes 500M
	
## 2. 限制cpu占用权重  --cpu-shares=10
	docker run --cpu-shares=10 --name=test1 laosuaidami/docker-stress --cpu 1 
	docker run --cpu-shares=5 --name=test2 laosuaidami/docker-stress --cpu 1