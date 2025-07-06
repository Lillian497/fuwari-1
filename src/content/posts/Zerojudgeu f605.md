---
title: Zerojudgeu f605. 1. 購買力
published: 2025-07-06
tags: [Zerojudgeu]
category: 程式解題日誌
draft: false
---

連結:https://zerojudge.tw/ShowProblem?problemid=f605
#  Zerojudgeu f605. 1. 購買力
```python
from sys import stdin
n,d=map(int,stdin.readline().split())
date=[]
c=0
an=[]
for i in range(n):
        list1=list(map(int,stdin.readline().split()))
        date.append(list1)
for o in date:
    if max(o)-min(o)>d:
        c+=1
        an.append(sum(o)//3)
print(c,sum(an))


```
