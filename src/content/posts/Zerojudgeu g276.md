---
title: Zerojudgeu g276. 2.  魔王迷宮-第二子題
published: 2025-07-06
tags: [Zerojudgeu]
category: 程式解題日誌
draft: false
---

連結:https://zerojudge.tw/ShowProblem?problemid=g276
#  Zerojudgeu g276. 2. 魔王迷宮-第二子題
```python
n,m,k=map(int,input().split())
date=[[0]*m for p in range(n)]
location=[]
location=[list(map(int,input().split())) for i in range(k)]

def put(location,date):
    for t in location:
        if 0<=t[0]<n and 0<=t[1]<m:
            date[t[0]][t[1]]=1

def move(location):
    for t in location:
            t[0],t[1]=t[0]+t[2],t[1]+t[3]

def explode(location,date):
    k=[]
    for p in location:
        w,q,r,d=p
        if 0 <= w < n and 0 <= q < m:
            if date[w][q]==1:
                k.append(p)
        else:
            k.append(p)
    for b in location:
        if 0<=b[0]<n and 0<=b[1]<m:
            if date[b[0]][b[1]]==1:
                date[b[0]][b[1]]=0

##    print(f"k={k}")
##    print(location)
    for g in k:
        location.remove(g)

while len(location)!=0:
    put(location,date)
##    print(f"date={date}")
    move(location)
##    print(f"location={location}")
    explode(location,date)
##    print(f"location,date={location},{date}")



list3=[[False]*m for e in range(n)]
for u in range(n):
    for j in range(m):
        if date[u][j]==1:
            list3[u][j]=True
list4=[date[o][d] for o in range(n) for d in range(m) if list3[o][d]==True]
print(len(list4))

```
