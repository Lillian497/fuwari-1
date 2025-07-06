---
title: APCS  第2題 矩陣轉換 105 年3月5日 程式設計實作題 
published: 2025-07-06
tags: [APCS考古題]
category: 程式解題日誌
draft: false
---

連結:https://apcs.csie.ntnu.edu.tw/wp-content/uploads/2018/12/1050305APCSImplementation.pdf
#  第2題 矩陣轉換 
```python

def nine(date,R,C):
    out=[]
    for e in range(C): 
        list4=[]
        for u in range(R):  
            list4.append(date[u][C-e-1])
        out.append(list4)


    return out,C,R

def collape(date,R):
    for t in range(R//2):
        date[t],date[R-t-1]=date[R-1-t],date[t]
    return date


R,C,M=map(int,input().split())
date=[]
for i in range(R):
    list1=list(map(int,input().split()))
    date.append(list1)
move=list(map(int,input().split()))
move.reverse()
for w in move:
    if w==1:
        date=collape(date,R)
    elif w==0:
        date,R,C=nine(date,R,C)
print(R,C)
for t in date:
    print(*t)

```
