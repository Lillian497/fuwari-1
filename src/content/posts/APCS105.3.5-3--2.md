---
title: APCS 第3題 線段覆蓋長度-大測資  105 年3月5日 程式設計實作題 
published: 2025-07-06
tags: [APCS考古題]
category: 程式解題日誌
draft: false
---

連結:https://apcs.csie.ntnu.edu.tw/wp-content/uploads/2018/12/1050305APCSImplementation.pdf
#  第3題 線段覆蓋長度-大測資 
```python
n=int(input())

##n=5
##date=[[160,180],[150,200],[280,300],[300,330],[190,210]]
c=0
date=[]
for _ in range(n):
    list1=list(map(int,input().split()))
    date.append(list1)
##1.排序
##2.合併(交集)

def line(date):
    date.sort()

def mix(date,n,c):
    for t in range(n):
        if t!=n-1:
            if date[t][1]<date[t+1][0] :
                    c=c+date[t][1]-date[t][0]
            elif date[t][1]>date[t+1][1]:
                date[t+1][0]=date[t][0]
                date[t+1][1]=date[t][1]
                
            else:
                date[t+1][0]=date[t][0]
                
        else:
             c=c+date[t][1]-date[t][0]
             return c

line(date)
print(mix(date,n,c))

```
