---
title: Java小知识点总结
---

## 1.ConcurrentHashMap
    JDK1.7的 ConcurrentHashMap 底层采用 分段的数组+链表 实现，JDK1.8 采用的数据结构跟HashMap1.8的结构一样，数组+链表/红黑二叉树。
    在JDK1.7的时候，ConcurrentHashMap（分段锁） 对整个桶数组进行了分割分段(Segment)，每一把锁只锁容器其中一部分数据，多线程访问容器里不同数据段的数据，就不会存在锁竞争，提高并发访问率。 到了 JDK1.8 的时候已经摒弃了Segment的概念，而是直接用 Node 数组+链表+红黑树的数据结构来实现，并发控制使用 synchronized 和 CAS 来操作。（JDK1.6以后 对 synchronized锁做了很多优化） 整个看起来就像是优化过且线程安全的 HashMap，虽然在JDK1.8中还能看到 Segment 的数据结构，但是已经简化了属性，只是为了兼容旧版本；
![2021_05_28_image.png](https://cdn.logseq.com/%2F1e5b0e5f-d368-4a5d-86eb-09a690ee15d72ebdfe18-330b-4a94-9c3f-8595c6f8036e2021_05_28_image.png?Expires=4775811559&Signature=ndwMYbA0GrZLrjG5QJdzRUJp9kNT9qLso7Pume-9xsa2lhkUkQaGZcLaP7dIJfLnCaV-Bu1B~EWqm~Q-ZkiMtizuAZEyw9lJKs1A7DV3NEOlq9u~FDp0t~KbOBP3b785BQYDz3R6VOaKKlCG2njbfcB0xaPulfS6nCE1GbMAvZXIvGINQNO4rmCfVqI9~sdYsGfBJzLn17PJ6kilBpllHOxzQY3TUIoD2X5sLUCO8Zx4hG2s0zFsPDai9A-zoJB0vo60-2O~bWJC2tkaVZ4N7mjA4tISKYVJKgX2zjQCIJRE~jxcr0YygveZimZ0-gStCVmqd~JoE1c4iAHMMklTnw__&Key-Pair-Id=APKAJE5CCD6X7MP6PTEA)
## 2.HashTable
    Hashtable 和 JDK1.8 之前的 HashMap 的底层数据结构类似都是采用 数组+链表 的形式，数组是 HashMap 的主体，链表则是主要为了解决哈希冲突而存在的；Hashtable(同一把锁) :使用 synchronized 来保证线程安全，效率非常低下。当一个线程访问同步方法时，其他线程也访问同步方法，可能会进入阻塞或轮询状态，如使用put 添加元素，另一个线程不能使用 put 添加元素，也不能使用 get，竞争会越来越激烈效率越低。
