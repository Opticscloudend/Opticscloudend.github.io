---
layout:     post
title:      大光圈高品质1.5倍变焦投影物镜设计
subtitle:   积木搭建法
date:       2016-08-01
author:     jackfy
header-img: img/lens_01.jpg
catalog: true
tags:
    - zoom
    - projector
    - object lens
---

#### 简介
- 积木设计方法简介
- 系统参数
- 开始点
- 优化
- 多重结构
- 变焦曲轮线
#### 积木设计方法简介
- 这种设计方法从大部分平行板开始，设计者设定的参数进行简单优化，如焦距、后焦距、畸变等；同时根据像差、F/#要求，消色差匹配等初步分配材质；最初得出一个初始结果，这个结果依赖初始条件，
  例如平板之间的厚度等；不同的初始条件，有不同的初始结构；在开始阶段，可以尝试不同条件，得多个初始结构；选初始结构，进一步优化，同时分析像差。当系统无法进一步改善时，赋予元件非球面，
  对 系统性能有比较大帮助的，利用球面元件或者胶合面代替；个人称搭积木法。
 

#### 系统参数
- 

###### 解压
```bash
cd /usr/local/

tar -zxvf mongodb-linux-x86_64-rhel70-4.0.0.tgz 
```
###### 重命名文件夹
```bash
mv mongodb-linux-x86_64-rhel70-4.0.0 mongodb4.0.0
```
###### 创建日志目录和数据文件目录
```bash
cd /usr/local/mongodb4.0.0/

mkdir -p data/logs

mkdir -p data/db
```
###### 指定配置文件
- 先在你的windows系统桌面上准备一个文件mongodb.conf，移动阿里云服务器目录下：/usr/local/mongodb4.0.0/
```
#端口号(默认的端口号是27017)
port=27017

#数据目录
dbpath=/usr/local/mongodb4.0.0/data/db

#日志目录（指定mongodb.log文件名，系统会自动创建）
logpath=/usr/local/mongodb4.0.0/logs/mongodb.log

#设置后台运行
fork=true 

#日志输出方式（写日志的模式：设置为true为追加。默认是覆盖。如果未指定此设置，启动时MongoDB的将覆盖现有的日志文件。）
logappend=true 

#开启认证（默认是false,不需要认证的，这里开启认证是为了安全性）
auth=false
```
###### 启动MongoDB
```bash
cd /usr/local/mongodb4.0.0/bin/

./mongod --config ../mongodb.conf
```
- 如果启动成功，你会看到以下内容：
    ```bash
    2019-08-30T10:38:27.567+0800 I CONTROL  [main] Automatically disabling TLS 1.0, to force-enable TLS 1.0 specify --sslDisabledProtocols 'none'
    about to fork child process, waiting until server is ready for connections.
    forked process: 32667
    child process started successfully, parent exiting
    ```
- 通过ps aux |grep mongodb命令查看mongodb进程是否开启
    ```bash
    ps aux |grep mongodb
    root     32667  4.0  2.6 1068176 50476 ?       Sl   10:38   0:00 ./mongod --config ../mongodb.conf
    root     32694  0.0  0.0 112708   988 pts/0    R+   10:38   0:00 grep --color=auto mongodb
    ```
###### 进入终端操作数据库
```bash
cd /usr/local/mongodb4.0.0/bin/

./mongo --port=27017
MongoDB shell version v4.0.0
connecting to: mongodb://127.0.0.1:27017
MongoDB server version: 4.0.0
Welcome to the MongoDB shell.
For interactive help, type "help".
For more comprehensive documentation, see
	http://docs.mongodb.org/
Questions? Try the support group
	http://groups.google.com/group/mongodb-user
> show dbs
> show dbs
> exit
bye
```
