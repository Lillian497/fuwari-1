---
title: Zerojudgeu f313. 2. 人口遷移
published: 2025-07-06
tags: [Zerojudgeu]
category: 程式解題日誌
draft: false
---

連結:https://zerojudge.tw/ShowProblem?problemid=f313
#  Zerojudgeu f313. 2. 人口遷移
```python
def move(date,C,k):
    mov=[]
    for u in date:
        add=[]
        for t in u:
            if t==-1 or t//k==0:
                add.append(0)
            else:
                add.append(t//k)
        mov.append(add)
    return mov

def new(date,mov,R,C):
    for y in range(R+2):
        for j in range(C+2):
            p=0
            l=0
            if date[y][j]==-1:
                continue
            else:
                if date[y-1][j]!=-1:
                    p+=1
                if date[y+1][j]!=-1:
                    p+=1
                if date[y][j-1]!=-1:
                    p+=1
                if date[y][j+1]!=-1:
                    p+=1
                date[y][j]=date[y][j]-mov[y][j]*p+mov[y+1][j]+mov[y][j+1]+mov[y-1][j]+mov[y][j-1]
            
##date1=[[-1, -1, -1,-1,-1], [-1, 10, 2, -1, -1], [-1, 5, -1, 2, -1], [-1,-1, -1, -1,-1]]   
##mov1=[[0, 0, 0,0,0], [0, 2, 0, 0, 0], [0, 1, 0, 0, 0], [0, 0, 0,0,0]]
##new(date1,mov1,2,3)
##print(date1)

from sys import stdin
R,C,k,m=map(int,stdin.readline().split())
date=[[-1]*(C+2)]
for i in range(R):
    list2=[-1]
    list1=list(map(int,stdin.readline().split()))
    for i in list1:
        list2.append(i)
    list2.append(-1)
    date.append(list2)
date.append([-1]*(C+2))
ans=[]
for e in range(m):
    o=move(date,C,k)
    new(date,o,R,C)
for t in date:
    for l in t:
        if l!=-1:
            ans.append(l)
ans.sort()
print(ans[0])
print(ans[-1])


```
