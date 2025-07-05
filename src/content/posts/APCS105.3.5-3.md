---
title: APCS 105 年3月5日 第3題 程式設計實作題 
published: 2025-07-04
tags: [APCS考古題]
category: 程式解題日誌
draft: false
---
連結:https://apcs.csie.ntnu.edu.tw/wp-content/uploads/2018/12/1050305APCSImplementation.pdf
# 第3題 線段覆蓋長度 -小測資(前半題)
```markdown
N=int(input())
list3=[]
list2=[]
list4=[]
for i in range(N):
  list1=list(map(int,input().split()))
  list2.append(list1)
for t in range(1001):
  list3.append(t)
for y in list2:
  if y[0]==y[-1]:
    pass
  else:  
    for u in range(y[0]+1,y[-1]+1):
      try:
        list3.remove(u)
      except:
        pass
print(1001-len(list3))


```
