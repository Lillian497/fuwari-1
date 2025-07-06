---
title: Zerojudgeu f579. 1. 購物車
published: 2025-07-06
tags: [Zerojudgeu]
category: 程式解題日誌
draft: false
---

連結:https://zerojudge.tw/ShowProblem?problemid=f579
#  Zerojudgeu f579. 1. 購物車
```python
def see(a,b,pe,count):
    a_have=0
    b_have=0
    for e in pe:
        if e==a:
            a_have+=1
        elif e==b:
            b_have+=1
        elif e==-a:
            a_have-=1
        elif e==-b:
            b_have-=1
    if a_have!=0 and b_have!=0:
        count.append(1)



from sys import stdin
a,b=map(int,stdin.readline().split())
n=int(input())
date=[]
for _ in range(n):
    list1=list(map(int,stdin.readline().split()))
    date.append(list1)
count=[]

for t in date:
    see(a,b,t,count)


print(len(count))

```
