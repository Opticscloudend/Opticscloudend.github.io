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
- 多重结构---长中短焦
- 变焦曲轮线
#### 积木设计方法简介
- 这种设计方法从大部分平行板开始，设计者设定的参数进行简单优化，如焦距、后焦距、畸变等；同时根据像差、F/#要求，消色差匹配等初步分配材质；最初得出一个初始结果，这个结果依赖初始条件，
  例如平板之间的厚度等；不同的初始条件，有不同的初始结构；在开始阶段，可以尝试不同条件，得多个初始结构；选初始结构，进一步优化，同时分析像差。当系统无法进一步改善时，赋予元件非球面，
  对 系统性能有比较大帮助的，利用球面元件或者胶合面代替；个人称搭积木法。
 

#### 系统参数
- 变焦范围：30-45mm
- F/#：2-2.2
- 对角线场：+/-17.5mm
- 总长： less than 230mm
- vignitting at all field: 0.7
- pixel: about 10um
- visible Spectrum
- distortion at all field: <3%


###### 平板到初始结构

![1682160290343](https://user-images.githubusercontent.com/131378528/233779418-674ae366-76d7-406b-a1bb-e1dd8c8a1584.png)

###### 优化长焦

![1682160621305](https://user-images.githubusercontent.com/131378528/233779718-26f3fa97-82e9-40da-be95-958a164dacf0.png)

![1a243897b6fb7662e9ada43e1e85a54](https://user-images.githubusercontent.com/131378528/233779759-ce95694c-2632-4684-8404-e5d311574bd1.png)

###### 全段焦优化

![1682160763027](https://user-images.githubusercontent.com/131378528/233779866-b66d8295-83d7-4e60-868f-fe8a6cb49f71.png)

![c0e6af6f23a9deb0976c019706cdeeb](https://user-images.githubusercontent.com/131378528/233779901-91215995-f34d-468e-bef3-6ab084e45e8a.png)

###### 指定配置文件

```
###### 启动MongoDB



###### 进入终端操作数据库

