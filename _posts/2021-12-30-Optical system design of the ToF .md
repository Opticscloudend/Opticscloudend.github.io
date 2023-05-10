---
layout:     post
title:      [Optical system design of the ToF]
subtitle:   [ part 2]
date:       [2021-12-30]
author:    jackfy
header-img: img/blog_Lucy.jpg
catalog: true
tags:
    - ToF
    - system
    - optical design
    - zemax
    - Sensor
    - laser
    
---
### Introduction

光学在ToF深度感测相机中起着至关重要的作用，光学设计决定了最终系统的复杂性和可行性及其性能。在ToF相机中，来自振幅调制光源的光被光学系统视场内的物体反射，并且测量发射波形和反射波形之间的相位差。通过在多个调制频率下测量相位差，可以计算每个像素的深度值。相位差是通过使用像素内光子混合解调来测量在不同相对延迟下发射波形和接收波形之间的相关性获得的。
            
![image](https://github.com/Opticscloudend/opticscloudend.github.io/assets/131378528/46d02418-343f-461e-aa72-720c26516b69)


图2显示了光学系统布局。主要分为两个主要模块：成像模块和照明模块。

![image](https://github.com/Opticscloudend/opticscloudend.github.io/assets/131378528/772bd15e-2ff4-471a-829d-b341d6296fb1)

### 照明模块

照明模块主要是使用垂直腔发射激光二极管光源（VCSEL），其主要的优点是发射波长对温度不敏感，稳定，带宽比较窄，成本比较低。应用的波长主要有850nmh和940nm，

- （1）波长选择主要考虑系统的sensor两点：

- Sensor的量子效率（QE， Quantum Efficiency)）
- sensor的响应（R, Resposivity)

![image](https://github.com/Opticscloudend/opticscloudend.github.io/assets/131378528/94240d35-4230-4214-9d72-d4a51bd71c50)
在相同的功率下，高的QE和R值，信噪比比较低，有利于远距离和低发射物体的探测。
-  (2)人眼感知
人眼对近红外（NIR）不是很敏感，但是人眼可以感知到850nm，而对940nm感知不到。

- （3）环境光
环境光主要来之于白天的阳光，阳光除了主要的可见光之外，还有一部分的NIR光，NIR对探测有严重的影响，但是非常幸运，NIR 920nm~960nm经过大气层，绝大部分被大气吸收。
与850 nm区域相比，该区域的太阳辐照度不到一半(见图3)。在室外应用中，在940 nm处操作ToF系统可以提供更好的环境抗光性，并带来更好的深度传感性能。

![image](https://github.com/Opticscloudend/opticscloudend.github.io/assets/131378528/45fbb398-3679-4ee1-ac51-53f6052aa689)



