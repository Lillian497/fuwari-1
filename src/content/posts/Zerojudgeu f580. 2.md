---
title: Zerojudgeu f580. 2. 骰子
published: 2025-07-06
tags: [Zerojudgeu]
category: 程式解題日誌
draft: false
---

連結:https://zerojudge.tw/ShowProblem?problemid=f580
#  Zerojudgeu f580. 2. 骰子
```python
import copy
def in_onelow(o,dice):
    dice1=copy.deepcopy(dice)
    dice[0]=dice1[1][3]
    dice[1]=[dice1[1][0],dice1[0],dice1[1][2],dice1[2]]
    dice[2]=dice1[1][1]
    return dice

def in_twolow(o,dice):
    dice1=copy.deepcopy(dice)
    dice[1].pop(3)
    dice[1].insert(0,dice1[1][3])
    return dice

def in_same(i,dice):
    c=dice[i[0]-1]
    dice[i[0]-1]=dice[i[1]-1]
    dice[i[1]-1]=c
    return dice

from sys import stdin
n,m=map(int,stdin.readline().split())
date=[]
for _ in range(m):
    list1=list(map(int,stdin.readline().split()))
    date.append(list1)

dice=[]
for y in range(n):
    dice.append([3,[5,1,2,6],4])
##print(dice)
for i in date:
##    if n!=1:
        if i[1]==-1:
            dice[i[0]-1]=in_onelow(i[0],dice[i[0]-1])
        elif i[1]==-2:
            dice[i[0]-1]=in_twolow(i[0],dice[i[0]-1])
        elif i[0]>0 and i[1]>0:
            dice=in_same(i,dice)
##    else:
##        if i[1]==-1:
##            print(dice)
##            dice[0]=in_onelow(i[0],dice[0])
##        elif i[1]==-2:
##            dice[0]=in_twolow(i[0],dice[0])
##        elif i[0]>0 and i[1]>0:
##            dice[0]=in_same(i,dice[0])
##        print(f"end={dice}")
p=0
for j in dice:
    p+=1
    if p!=n:
        print(j[1][1],end=" ")
    else:
        print(j[1][1])
    

```
