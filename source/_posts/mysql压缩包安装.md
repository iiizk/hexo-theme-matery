---
title: mysql压缩包安装
date: 2022-03-25 21:02:19
tags:
---
## 这次讲的是mysql压缩包安装方式。此次安装的都是5.7版本的。
### mysql压缩包
### 下载mysql5.7压缩包
`https://downloads.mysql.com/archives/community/`
或者
`https://github.com/iiizk/download/releases/download/db/mysql-5.7.36-winx64.zip`
![m1](/images/mysql/m1.png)
我们解压到E盘
设置环境变量
![m2](/images/mysql/m2.png)
![m3](/images/mysql/m3.png)
创建配置文件my.ini
```
[mysql]
#设置mysql客户端默认字符集
default-character-set=utf8 
[mysqld]
#设置3306端口
port = 3306 
#设置mysql的安装目录
basedir=E:\mysql-5.7.36-winx64
#设置mysql数据库的数据的存放目录
datadir=E:\mysql-5.7.36-winx64\data
#允许最大连接数
max_connections=200
#服务端使用的字符集默认为UTF8
character-set-server=utf8
#创建新表时将使用的默认存储引擎
default-storage-engine=INNODB
explicit_defaults_for_timestamp=1
innodb_flush_method=normal
```
## 初始化MySQL
### 以下记得用管理员cmd

```
mysqld --initialize-insecure
这样可以初始化root用户密码为空

mysqld –initialize会生成一个随机密码
这里我们用mysqld –initialize-insecure
```

### 这里如果报错找不到MSVCP120.dll 缺少vc++运行库我们装一个
`https://github.com/iiizk/download/releases/download/db/VisualCppRedist_AIO_x86_x64_29.zip`

### 如果之前安装过，需要先卸载
`mysqld --remove`

### 安装
`mysqld --install`

### 启动mysql服务
`net start mysql`

### 连接MySQL
`mysql -uroot -p`
密码空的直接回车就好
修改密码
```
mysql>
ALTER USER 'root'@'localhost' IDENTIFIED BY '123456';
flush privileges;
```
### 重新登录
`mysql -uroot -p123456`
![m4](/images/mysql/m4.png)