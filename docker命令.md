# docker命令
1. sudo docker image ls  (or) docker images               查看系统所有image
2. sudo docker pull ubuntu:14.04         				安装 ubuntu 14.04 image
3. docker image rm [image ID]  (or) docker rmi [image ID] 删除image
3. sudo docker pull bitnami/wordpress    				安装bitnami的wordpress image
4. docker build -t xiaopeng163/hello-world .  			在当前目录编译Dockerfile
5. docker history [image_ID]
6. docker run xiaopeng163/hello-world     				docker运行image
7. docker run -it ubuntu       							  交互式运行ubuntu container
7. docker container ls                   				当前本地正在运行的程序
8. docker container ls -a  or docker ps -a              所有的容器，包括正在运行的，和已经退出的
9. docker container rm [container_ID]  (or)  docker rm [container_ID]   删除容器，包括正在运行的，和已经退出的


10. docker container ls -aq (or) docker container ls -a|awk{'print$1'}
11. docker rm $(docker container ls -aq)     # 删除所有container
12. docker rm $(docker container ls -f 'status=exited' -q)    删除已经结束的container
13. docker container commit (or) docker commit
