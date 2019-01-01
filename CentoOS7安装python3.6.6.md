## 1. 下载Python包
  	wget https://www.python.org/ftp/python/3.6.6/Python-3.6.6.tgz
  
## 2. 解压Python包
	tar -xzvf Python-3.6.6.tgz -C  /tmp 
	
## 3. 进入路径
	cd Python-3.6.6/
	
## 4. 安装gcc编译环境-->编译安装包
	1. yum install -y gcc (如果已经安装了gcc,这一步就不需要了)
	2. yum install openssl-devel -y (如果没有安装openssl-devel，在使用pip3时会报异常“locations that require TLS/SSL……”)
	3. ./configure --prefix=/usr/local 
	4. make
	
## 5. 安装到系统路径下
	1. 安装zlib相关依赖包: yum -y install zlib*  (如果没有安装，下一步会报错“zipimport.ZipImportError: can't decompress data; zlib not available”)
	2. make altinstall 
	
## 6. 建立软连接
	1. ln -s /usr/local/bin/python3.6 /usr/bin/python3
	2. ln -s /usr/local/bin/pip3.6 /usr/bin/pip3 

# 安装结束
