---
title: embeddings
---

## 对embedding的认识：
### 1.作用：
    1.1.实现将高维稀疏特征向量向低维稠密特征向量转换
    1.2.Embedding特征向量可以属于预训练部分，作为一种新的特征向量参与神经网络的训练
    1.3.Embedding可以提取user之间（或者user item or item）的相似度（从某种维度来看）
### 2.来源：
### 最先提出的是Embedding概念的是word2vec（字转向量），如何设计向量，在让不同字词保持**相对独立**的同时**计算彼此之间的相关联度**，解决不同字词保持相对独立的方法使用的是one-hot编码，即如果一件事物有N个选择（假设汉字有N个），则设置一个N维度的向量，每个汉字都只设置一个1，其他位置设置为0，比如吴（1，0，0，....，0），彦（0，1，.....，0），这导致了稀疏数据（神经网络难以学习），这时候提出两个模型：skip-gram和cbow。（前者是用一个词语作为输入，预测该词的上下文context；后者是拿一个词的context去预测这个词），如图：
### ![2021_05_29_image.png](https://cdn.logseq.com/%2F1e5b0e5f-d368-4a5d-86eb-09a690ee15d7f034e802-d974-4680-9ac2-828836461c022021_05_29_image.png?Expires=4775869737&Signature=LMAvQJrBwd1bIp9BiupWjpRJKqxJmD8LHapz2h0-YbigDgkZUiU2lpY2AWA3GbseiJg02crXPXGhJu1ourWHsP9-SDV0WKxcbchpvx6Wemov1S1WzMOmfOlX-pCcA~27x7UdfJYUAbj7l781i8CtkB2BVchhWMjUdUfapZsnPVbyAhocA1HWWldEqy0caEHDVmdc9hs7eeNwNiKixyA8O~w4CB8Y9qcwpXbfnOE~EGZUHrlmESy7aYCqmDKsph1LgAYfkSpC7Bs06ME5VnOCmiSIWgGA-CupYb0f3L~qfrEJmq2oKhF10m-TH68CQL3uZ5jPIue6W~Qq-9gepUR6Bw__&Key-Pair-Id=APKAJE5CCD6X7MP6PTEA)
### 借用这种方法，Embedding找到一个映射方式，实现了高维稀疏到低维稠密的变化，所以这部分训练的重点的是：得到Hidden layer的参数（神经网络的权重），用这个权重来代替之前v个维度的数据（这是可以唯一表示的）将one-hot的**V维降低到N维**；
###
