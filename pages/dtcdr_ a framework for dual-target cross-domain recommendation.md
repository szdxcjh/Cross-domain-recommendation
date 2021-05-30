---
title: DTCDR: A Framework for Dual-Target Cross-Domain Recommendation
---

## CDR部分：和迁移学习有异曲同工的感觉，似乎都是在某一个域的学习基础上对另外的域进行识别；
## 论文内容：dual-target  双域中每个域都有各自丰富的信息，如果能利用好这些信息就能两边（两个域）都提高准确率。
## 主要利用：rating 和 multi-source content information，生成user和item的rating 和 document的[[embeddings]]，接着，基于Multi-Task Learning（MTL），设计了一种embedding分享策略，结合和分享相同user的embeddings；
## 传统的CDR方法：
主要分为两类：content-based transfer and feature-based transfer
    1.基于内容的转移：利用不同的内容（比如评论和用户简介），匹配相似的user和item后构建桥梁，训练CF模型等；
    2.基于特征的转移：（概率矩阵分解，个性化贝叶斯排序）获取user/item的特征，通过域把相同或相似的
##
