---
title: DTCDR: A Framework for Dual-Target Cross-Domain Recommendation
---

## CDR部分：和迁移学习有异曲同工的感觉，似乎都是在某一个域的学习基础上对另外的域进行识别；
## 论文内容：dual-target  双域中每个域都有各自丰富的信息，如果能利用好这些信息就能两边（两个域）都提高准确率。
## 主要利用：rating 和 multi-source content information，生成user和item的rating 和 document的[[embeddings]]，接着，基于Multi-Task Learning（MTL），设计了一种embedding分享策略，结合和分享相同user的embeddings；
## 传统的CDR方法：
主要分为两类：
    1.
