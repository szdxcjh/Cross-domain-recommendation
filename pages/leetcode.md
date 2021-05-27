---
title: Leetcode
---

## 小技巧：
    1.在检测两个数字位的不同时可用以下方法：
## 
```clojure
int s = x^y,res = 0;//异或运算，不同为1
while(s != 0){
    res += s&1;//检测为1的位数；
    s >>= 1;
    }
```
