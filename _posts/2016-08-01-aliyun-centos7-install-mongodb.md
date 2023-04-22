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
- 这种设计方法从大部分平行板开始，设计者设定的参数进行简单优化，如焦距、后焦距、畸变等；同时更加像差、F/#要求，消色差技术初步分配材质；最初得出一个初始结果，这个结果依赖初始条件，例如平板之间的厚度等。
 
- 面向集合的存储：适合存储 JSON风格文件的形式
- 完整的索引支持：对任何属性可索引
- 复制和高可用性：支持服务器之间的数据复制，支持主-从模式及服务器之间的相互复制。复制的主要目的是提供冗余及自动故障转移
- 自动分片：支持云级别的伸缩性：自动分片功能支持水平的数据库集群，可动态添加额外的机器
- 丰富的查询：支持丰富的查询表达方式，查询指令使用JSON形式的标记，可轻易查询文档中的内嵌的对象及数组
- 快速就地更新：查询优化器会分析查询表达式，并生成一个高效的查询计划
- 高效的传统存储方式：支持二进制数据及大型对象（如照片或图片）

#### 在CentOS7上安装MongoDB
###### 下载地址
- [https://fastdl.mongodb.org/linux/mongodb-linux-x86_64-rhel70-4.0.0.tgz](https://fastdl.mongodb.org/linux/mongodb-linux-x86_64-rhel70-4.0.0.tgz)
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
