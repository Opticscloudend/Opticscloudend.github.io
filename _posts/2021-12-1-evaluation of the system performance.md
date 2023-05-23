---
layout:     post
title:      [Evaluation of the optical system performance]
subtitle:   [系统的成像质量我们主要考虑哪些指标？]
date:       [2021-12-09]
author:    jackfy
header-img: img/blog_Lucy.jpg
catalog: true
tags:
    - MTF
    - focus depth
    - spot RMS radius
    - spot GEO radius
    - light receptor cell
---
今年很快就过去了，今天谈谈系统的成像质量的评估；
我们在开始设计系统阶段，参数计算阶段，需要考虑，这个系统设计最终要到底什么样的指标性能。这样在整个设计过程中就有了方向。但是这性能指标不能定的太低，太低系统达不到要求；设定太高，也不好，系统会复杂，元件过多造成成本过高。所以要一个明确的指标
- MTF（调制函数）
MTF是评价系统性能重要指标之一，当我们确定了CCD/CMOS/DMD/Lcos等芯片元件时候，其CELlc
尺寸是知道的；那么最好预定MTF>=50%，其频率=1/（2*cell）,单位：lp/mm。是不是定得很高，是的；主要是考虑后期系统元件制造，组装等公差引起MTF下降。假如下降MTF=20%，那么最终系统还能保持在MTF>30%。各视场MTF尽量集中，分离不超过0.1比较好。整个频率范围MTF曲线平滑过渡。
- RMS Radius(弥散斑均方根半经)
  RMS R<=cell
- GEO 
  
  
