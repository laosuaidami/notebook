# Python原始虚拟环境（不太好用，只是记录一下）

## 1. 安装virtualenvwrapper
  	sudo apt-get install python-virtualenv
  	
## 2. 新建虚拟环境
	1. 使用系统默认Python环境(python2.7)新建
		virtualenv my_virtual  # my_virtual--> 自己虚拟环境的名字
		
	2. 使用指定Python环境新建
		virtualenv -p /usr/bin/python3 my_virtual
	
## 3. 激活虚拟环境
	source .env/bin/activate
	
## 4. 退出虚拟环境
	deactivate
	

# virtualenvwrapper 虚拟环境
## 1. 安装virtualenvwrapper
  	 pip install virtualenvwrapper
  	 
## 2. 编辑.bashrc文件
	1. 查找virtualenvwrapper.sh路径:  sudo find / -name virtualenvwrapper.sh  (我的电脑搜索结果：/usr/bin/virtualenvwrapper.sh)
	2. sudo vi .bashrc (打开.bashrc文件将下面两行添加到末尾)
		export WORKON_HOME=$HOME/.virtualenvs
		source /usr/bin/virtualenvwrapper.sh  # 特别注意 一定要用上边收到的路径！！！！！！！！！！！！！！
	3. source ~/.bashrc
	
## 3. 新建虚拟环境
	1. 使用系统默认Python环境(python2.7)新建
		mkvirtualenv my_virtual  # my_virtual--> 自己虚拟环境的名字
	2. 使用指定Python环境新建
		mkvirtualenv -p /usr/bin/python3 my_virtual
	3. source ~/.bashrc
	
## 4. 进入虚拟环境
	workon my_virtual
	
## 5. 退出虚拟环境
	deactivate
	
## 6. 删除虚拟环境
	rmvirtualenv my_virtual


# 结束



