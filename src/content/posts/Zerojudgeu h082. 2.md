---
title: Zerojudgeu h082. 2. 贏家預測-第一子題
published: 2025-07-06
tags: [Zerojudgeu]
category: 程式解題日誌
draft: false
---

連結:https://zerojudge.tw/ShowProblem?problemid=h082
#  Zerojudgeu h082. 2. 贏家預測-第一子題
```python
def judge(power,m,c):
    f=rank[c]
    s=rank[c+1]
    if power[f-1]*m[f-1]>=power[s-1]*m[s-1]:
        t=power[f-1]+power[s-1]*m[s-1]//(2*m[f-1])
        k=m[f-1]+power[s-1]*m[s-1]//(2*power[f-1])
        l=power[s-1]+power[s-1]//2
        h=m[s-1]+m[s-1]//2
        power[f-1]=t
        m[f-1]=k
        power[s-1]=l
        m[s-1]=h
        return rank[c],rank[c+1],c
    else:
        t=power[s-1]+power[f-1]*m[f-1]//(2*m[s-1])
        k=m[s-1]+power[f-1]*m[f-1]//(2*power[s-1])
        h=power[f-1]+power[f-1]//2
        l=m[f-1]+m[f-1]//2
        power[s-1]=t
        m[s-1]=k
        power[f-1]=h
        m[f-1]=l
        return rank[c+1],rank[c],c+1

from sys import stdin
n,m=map(int,stdin.readline().split())
power=list(map(int,stdin.readline().split()))
mm=list(map(int,stdin.readline().split()))
rank=list(map(int,stdin.readline().split()))


new=[]
j=0
while len(rank)!=1:
    c=-2
    if len (rank)%2!=0:
        y=rank[-1]
        j=-1
    for i in range(len(rank)//2):
        c+=2
        w,l,g=judge(power,mm,c)
        new.append(w)
##        print(f"w={w}")
    if len (rank)%2!=0:
        new.append(rank[-1])

    rank=new
    new=[]
##    print(f"rank={rank},power={power},mm={mm}")

print(*rank)
```
