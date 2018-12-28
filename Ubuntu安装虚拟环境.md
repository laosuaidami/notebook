
## 1. 安装virtualenvwrapper
  	1. yum install python-setuptools python-devel
  	2. pip install virtualenvwrapper
## 2. 编辑.bashrc文件
	1. 查找/virtualenvwrapper.sh路径:  whereis virtualenvwrapper.sh  (我的电脑搜索结果：/usr/bin/virtualenvwrapper.sh)
	2. sudo vi .bashrc (打开.bashrc文件将下面两行添加到末尾)
		export WORKON_HOME=$HOME/.virtualenvs
		source /usr/bin/virtualenvwrapper.sh  # 特别注意 一定要用上边收到的路径！！！！！！！！！！！！！！
	
## 3. 新建虚拟环境
	1. 使用系统默认Python环境(python2.7)新建
		mkvirtualenv my_virtual  # my_virtual--> 自己虚拟环境的名字
		
	2. 使用指定Python环境新建
		mkvirtualenv -p /usr/bin/python3 my_virtual
	
## 4. 进入虚拟环境
	workon my_virtual
	
	
## 5. 退出虚拟环境
	deactivate
	
## 6. 删除虚拟环境
	rmvirtualenv my_virtual


# 结束
