### 1. 进入ubuntu container
	docker run -it ubuntu:16.04    

### 2. 安装stress包    
	apt-get update && apt-get install -y stress
	stress --help    查看 stress 命令帮组
	
### 3. 创建进程  并打印信息
	stress --vm 1  表示创建1个进程
	stress --vm 1 --verbose 表示创建1个进程，并打印测试信息
	
