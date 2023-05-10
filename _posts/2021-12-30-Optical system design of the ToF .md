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


