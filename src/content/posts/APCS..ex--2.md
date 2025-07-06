---
title: APCS  題目範例 第2題 小群體 程式設計實作題 
published: 2025-07-06
tags: [APCS考古題]
category: 程式解題日誌
draft: false
---

連結:https://apcs.csie.ntnu.edu.tw/wp-content/uploads/2018/12/1060304APCSImplementation.pdf
#  題目範例 第2題 小群體
```python
N=int(input())
list2=[0]*N
date=list(map(int,input().split()))


def find(y,u,c,list2):
          if y==u:
              c+=1
              list2[y]=1
              return c
          else:
              list2[y]=1
              return find(date[y],u,c,list2)
c=0
for w in range(N):
          if list2[w]==0:
              y=date[w]
              c=find(y,w,c,list2)
          elif sum(list2)==N:
              break
print(c)
print("")

```
