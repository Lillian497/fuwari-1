---
title: Zerojudgeu g596. 2. 動線安排
published: 2025-07-06
tags: [Zerojudgeu]
category: 程式解題日誌
draft: false
---

連結:https://zerojudge.tw/ShowProblem?problemid=g596
#  Zerojudgeu g596. 2. 動線安排
```python
##加入木樁(0,1)
##[[0,-1,0,0],[0,0,0,0],[0,0,0,0]]
##
##加入木樁(2,1)
##[[0,-1,0,0],[0,0,0,0],[0,-1,0,0]]
##線
##[[0,-1,0,0],[0,2,0,0],[0,-1,0,0]]
##加入木樁(2,3)
##[[0,-1,0,0],[0,2,0,0],[0,-1,0,-1]]
##線
##[[0,-1,0,0],[0,2,0,0],[0,-1,1,-1]]
##移除木樁(2,1)
##[[0,-1,0,0],[0,2,0,0],[0,0,1,-1]]
##線
##[[0,-1,0,0],[0,0,0,0],[0,0,0,-1]]

def add_right(row,num,n,date):
    if num!=n-1:
        for u in range(n-num-1):
            if date[row][num+u+1]==-1:
                for t in range(u):
                    if date[row][num+t+1]==0:
                        date[row][num+t+1]=1
                    elif date[row][num+t+1]==2:
                        date[row][num+t+1]=3
                break
    if num!=0:
        for t in range(num):
            if date[row][num-t-1]==-1:
                for y in range(t):
                    if date[row][num-y-1]==0:
                        date[row][num-y-1]=1
                    elif date[row][num-y-1]==2:
                        date[row][num-y-1]=3
                break
def cup_right(row,num,n,date):
    if num!=n-1:
        for u in range(n-num-1):
            if date[row][num+u+1]==-1:
                for t in range(u):
                    if date[row][num+t+1]==1:
                        date[row][num+t+1]=0
                    elif date[row][num+t+1]==3:
                        date[row][num+t+1]=2
                break
    if num!=0:
        for t in range(num):
            if date[row][num-t-1]==-1:
                for y in range(t):
                    if date[row][num-y-1]==1:
                        date[row][num-y-1]=0
                    elif date[row][num-y-1]==3:
                        date[row][num-y-1]=2
                break
    
##row1=0
##row2=1
##num1=0
##num2=1
##num3=2
##num4=3
##n=4
##date1=[[0,-1,0,0],[0,0,0,0]]
##date2=[[-1,-1,0,0],[0,0,0,0]]
##date3=[[0,-1,-1,0],[0,0,0,0]]
##date4=[[0,-1,-1],[0,0,0,0]]
##
##date5=[[-1,3,-1,0],[0,0,0,0]]
##
##date=date5
##num=num3
##row=row1
##cup_right(row,num,n,date)
##print(date)

def add_up(row,num,m,date):
    if row!=m-1:
        for u in range(m-row-1):
            if date[row+u+1][num]==-1:
                for t in range(u):
                    if date[row+t+1][num]==0:
                        date[row+t+1][num]=2
                    elif date[row+t+1][num]==1:
                        date[row+t+1][num]=3
                break
    if row!=0:
        for t in range(row):
            if date[row-t-1][num]==-1:
                for y in range(t):
                    if date[row-y-1][num]==0:
                        date[row-y-1][num]=2
                    elif date[row-y-1][num]==1:
                        date[row-y-1][num]=3
                break

def cup_up(row,num,m,date):
    if row!=m-1:
        for u in range(m-row-1):
            if date[row+u+1][num]==-1:
                for t in range(u):
                    if date[row+t+1][num]==2:
                        date[row+t+1][num]=0
                    elif date[row+t+1][num]==3:
                        date[row+t+1][num]=1
                break
    if row!=0:
        for t in range(row):
            if date[row-t-1][num]==-1:
                for y in range(t):
                    if date[row-y-1][num]==2:
                        date[row-y-1][num]=0
                    elif date[row-y-1][num]==3:
                        date[row-y-1][num]=1
                break
##row=2
##num=0
##m=4
##date1=[[0,0,0,0],[-1,0,0,0],[0,0,0,0],[0,0,0,0]]
##date2=[[-1,0,0,0],[-1,0,0,0],[0,0,0,0],[0,0,0,0]]
##date3=[[0,0,0,0],[-1,0,0,0],[-1,0,0,0],[0,0,0,0]]
##date4=[[0,0,0,0],[-1,0,0,0],[2,0,0,0],[-1,0,0,0]]
##date5=[[-1,0,0,0],[3,0,0,0],[2,0,0,0],[-1,0,0,0]]
##date6=[[-1,0,0,0],[2,0,0,0],[-1,0,0,0],[0,0,0,0]]
##date=date6
##cup_up(row,num,m,date)
##print(date)

from sys import stdin
m,n,h=map(int,stdin.readline().split())
step=[]
ans=[]
for _ in range(h):
    list1=list(map(int,stdin.readline().split()))
    step.append(list1)
date=[]
for i in range(m):
    list2=[0]*n
    date.append(list2)
for w in step:
    r,c,t=w[0],w[1],w[2]
    if t==0:
        date[r][c]=-1
        add_right(r,c,n,date)
        add_up(r,c,m,date)
    else:
        cup_right(r,c,n,date)
        cup_up(r,c,m,date)
        date[r][c]=0
    c=0
    for u in date:
        for g in u:
            if g!=0:
                c+=1
    ans.append(c)
print(max(ans))
print(ans[-1])

```
