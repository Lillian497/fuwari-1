---
title: Zerojudgeu h081. 1. 程式交易
published: 2025-07-06
tags: [Zerojudgeu]
category: 程式解題日誌
draft: false
---

連結:https://zerojudge.tw/ShowProblem?problemid=h081
#  Zerojudgeu h081. 1. 程式交易
```python
def see(have,y,d,count,up):
    if have!=0 and have+d<=y:
        count+=y-have
        have=0
        up=y
    elif have==0 and up-d>=y:
        have=y


    return have,count,up
    

from sys import stdin
n,d=map(int,stdin.readline().split())
cont=list(map(int,stdin.readline().split()))

have=cont[0]
count=0
up=0
for i in range(n-1):

    have,count,up=see(have,cont[i+1],d,count,up)


print(count)


```
