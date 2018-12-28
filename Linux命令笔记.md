# Linux命令笔记

1. sudo groupadd  [用户组]   增加用户组
2. sudo gpasswd -a vagrant docker  将vagrant用户添加到docker用户组
3. groups [username]：查看该用户所属用户组     
4. sudo adduser [username]：添加新用户     
5. sudo usermod -G [用户组] [username]：把用户添加到用户组     
6. sudo usermod -G sudo Kobe：把科比添加到 sudo 用户组     
7. sudo deluser [username]：删除用户，如果同名用户组没有其它成员，同时该用户组也没了     
8. sudo gpasswd -d [username] [用户组]：从用户组中删除用户     
9. su [username]：切换用户到当前目录    
10. su -l [username]：切换用户到用户家目录   【
11. Ctrl D】 / exit：退出当前用户     
12. sudo su：使当前用户进入 root 
13. chmod [777] [file]：修改文件权限     
14. sudo chown [username] [file]：修改文件所有者（sudo 组用户才有此权限）
