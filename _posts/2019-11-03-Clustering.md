---
layout:     post
title:      Clustering
subtitle:   聚类算法
date:       2019-11-04
author:     Paul
header-img: img/post-bg-os-metro.jpg
catalog: true
tags:
    - Algorithm
    - Clustering
    - Unsupervised
    - ML
---
## Hierarchical Clustering
#### Agglomerative

Inter-Cluster Distance

    Method | Strenth | Limitation
    ---|---|---|
    MIN|less susceptible to cluster size|connected
    MAX|connected|less susceptible to cluster size
    Average|less susceptible to noise and outliers|
    Ward's Method|

Centroid vs. Clustroid

Termination condition:

  - Diameter = max distance between porints in the cluster
  - Radius = max distance of point from centroid or clustroid
  - Density = # of points per unit volumne

#### Divisive

#### Pros & Cons
   - Pros:
   - Cons: Does not work well for large datasets due to computation complexity

## Point Assignment
#### Center Selection Problem (k-center)
Greedy-center-selection

    Limitation: susceptive to outliers

#### Partitional Clustering: K-means Clustering

- How to decide value of k: average distance to centroids
- How to pick the initial k points:
  - Sampling: sample data + Hierarchical Clustering to get k clusters and k centroids
  - Pick dispersed set of points

#### K-means++

## DBSCAN
Core, Border, Noise Points

## More

#### EM
#### GMM
#### Spectral Clustering



## 参考资料

#### 已看论文

#### 待看论文

#### 已看文章

#### 待看文章

#### Q
- Local Search?
