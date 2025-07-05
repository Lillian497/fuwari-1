---
title: APCS  105年10月29日 第2題 程式設計實作題 
published: 2025-07-04
tags: [APCS考古題]
category: 程式解題日誌
draft: false
---
連結:https://apcs.csie.ntnu.edu.tw/wp-content/uploads/2018/12/1051029APCSImplementation.pdf
# 第2題  最大和
```markdown
N,M=map(int,input().split())
list1=[]
s=0
list3=[]
for i in range(N):
    list2=list(map(int,input().split()))
    list1.append(list2)
for t in list1:
    s+=max(t)
print(s)
for p in list1:
    if s%max(p)==0:
        list3.append(max(p))
if len(list3)==0:
    print(-1)
else:
    print(*list3)


```
