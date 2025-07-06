---
title: APCS  第3題 定時K彈 105 年10月29日 程式設計實作題 
published: 2025-07-06
tags: [APCS考古題]
category: 程式解題日誌
draft: false
---

連結:https://apcs.csie.ntnu.edu.tw/wp-content/uploads/2018/12/1051029APCSImplementation.pdf
#  第3題 定時K彈
```python
N,M,K=map(int,input().split())
list1=list(i+1 for i in range(N))
n=0
for t in range(K):
    n+=M-1
    if n>len(list1)-1:
        n=n%len(list1)
    list1.pop(n)
if n>len(list1)-1:
        n=n%len(list1)
print(list1[n])
print("")

```
