---
layout:     post
title:      ---
layout:     post
title:      TracePro之Backlight入门设计
subtitle:   Backlight Design
date:       2015-10-01
author:     jackfy
header-img: img/lens_03.jpg
catalog: true
tags:
    - Lightguide
    - Tracepro
    - Backlihgt
    - Lightpanel
---

#### TracePro之Diffuser入门设计

### （一）	TracePro的基本模拟流程
1、	建立需要模拟的3D对象-----------机械工程师提供或者按照工程师给的结构空间自行设计。
2、	定义好光学特性----------包括diffuser材料，holder材料反射特性。
3、	定义LED光源------------包括波长，光线数量，配光曲线。
4、	建立目标接收面-----------即是LCD接光面（一般定义LCD底面）
5、	建立pattern分布。
6、	光线追迹
7、	对模拟结果进行分析。
### （二）	实例操作
         在tracepro打开设计好的3D文件。

  
![image](https://user-images.githubusercontent.com/131378528/233787238-34194759-2f9f-4622-b64c-7f0bc12aa7c3.png)


 ![image](https://user-images.githubusercontent.com/131378528/233787246-d3c65e04-da2a-4e78-84f0-8eb3096dda3a.png)



### 1、定义diffuser材料：PMMA：
 
 ![image](https://user-images.githubusercontent.com/131378528/233787330-7a921d22-ef97-4d5c-881c-f7145b864c02.png)

### 2、定义holder反射面
 
![image](https://user-images.githubusercontent.com/131378528/233787350-979a7fed-a013-4305-8896-f97cd011bcbb.png)


### 3、定义LED光源：光线数量100000条，光通量0.1

 ![image](https://user-images.githubusercontent.com/131378528/233787385-7575df73-5a1b-45f0-9d15-3caa2019a9da.png)


### 4、选择LCD底面为接收面能量面

### 5、设计pattern分布；定义diffuser底面为pattern面，
方法1、pattern以下分布。Tracepro----reptile数据

方法2、或者应用matlab 编写 texture文件，这里提一下，ray在整个diffuser内部跑过的能力分布图，提前其能量数据

利用matlab编写对应的texture的分布密度数据。这样调整比较方便。

 ![image](https://user-images.githubusercontent.com/131378528/233787431-7c912bad-78c9-48dc-a317-3a984b8198da.png)


### 6、追迹200000条光线

![image](https://user-images.githubusercontent.com/131378528/233787637-1c5f5503-2104-4eea-a0ff-bc5321605628.png)


#### 7、结果
 
 ![image](https://user-images.githubusercontent.com/131378528/233787652-eeefe0a7-422e-4804-b5dd-6231a4b6e79e.png)


模拟结果中可获得照度图，其中的数据包括照度平均值Ave、最小值Min和最大值Max

一般地：Ave/Max>0.7可以接受。

软件具体操作请参阅User Manual; LED配光请参考User Manual或者官方样例。
