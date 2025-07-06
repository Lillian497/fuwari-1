---
title: APCS  第3題 數字龍捲風 程式設計實作題 
published: 2025-07-06
tags: [APCS考古題]
category: 程式解題日誌
draft: false
---

連結:https://apcs.csie.ntnu.edu.tw/wp-content/uploads/2018/12/1060304APCSImplementation.pdf
#  題目範例 第3題  數字龍捲風
```python
N=int(input())
x=int(input())
date=[]
for _ in range(N):
    list1=list(map(int,input().split()))
    date.append(list1)

##N=5
##x=0
##date=[[3,4,2,1,4],[4,2,3,8,9],[2,1,9,5,6],[4,2,3,7,8],[1,2,6,4,3]]
m=N//2
n=N//2
list2=[date[m][n]]
def way(date,x,n,m):
    if x==0:
        n-=1
    elif x==1:
        m-=1
    elif x==2:
        n+=1
    else:
        m+=1
    return n,m
##x,n,m=way(date,x,n,m)
##print(n,m,x)
##(5+4*((N-3)//2))//2
for k in range(N-1):
    for _ in range(k+1):
        n,m=way(date,x,n,m)
        list2.append(date[m][n])
    x+=1
    x=x%4
    for _ in range(k+1):
        n,m=way(date,x,n,m)
        list2.append(date[m][n])
    x+=1
    x=x%4
for _ in range(N-1):
        n,m=way(date,x,n,m)
        list2.append(date[m][n])

for j  in list2:
    print(j,end="")

```
