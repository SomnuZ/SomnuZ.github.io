---
layout:     post
title:      Neural Network Essentials
subtitle:   神经网络基础
date:       2019-11-03
author:     Paul
header-img: img/post-bg-hacker.jpg
catalog: true
tags:
    - ML
    - Nerual Network
---
## 训练过程
1. 准备样本
   1. 标准化
   2. Z score
   3. He
   4. Xnvier

2. 网络设计和评估
   - Activation
     - relu
     - sigmoid
     - softmax (概率化)
   - kernel_initializer & bias_initializer
     - Glorot uniform (default)
   - kernel_regularizer & bias_regularizer
     - None (default)
     - L1 or L2 regularizer
   - optimizer ? dynamic learning rateλ
     - λ=λe
     - Adam
   - loss
     - mse
     - crossentropy
   - matrics
     - confusion matrix
  
3. 训练
   - train validate test split
     - train
     - validate: validation_steps=3?
     - test
   - input data 
     - numpy array
     - tf.data.dataset: dataset.repeat()?

## 梯度
- 梯度消失
  - 靠近输入层
  - 全连接NN，layer太多
  - sigmoid容易产生梯度消失，ReLu不容易
- 梯度爆炸
  - 未做参数truncated_normal

## 参考资料

#### 已看论文
- 机器学习驱动的基本面量化投资研究 - 李斌，邵新月，李玥阳

#### 待看论文
- Lee and So，2015
- 张然和汪荣飞，2017

#### 已看文章

#### 待看文章
