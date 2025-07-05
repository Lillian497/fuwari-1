---
title: APCS 105年3月5日 程式設計實作題 
published: 2025-07-04
tags: [APCS考古題]
category: 程式解題日誌
draft: false
---
連結:https://apcs.csie.ntnu.edu.tw/wp-content/uploads/2018/12/1050305APCSImplementation.pdf
# 第1題 成績指標 
```markdown
n=int(input())
list1=list(map(int,input().split()))
list1.sort()
list2=[]
list3=[]
print(*list1)
for i in list1:
  if i<60:
    list2.append(i)
  else:
    list3.append(i)
if len(list2)==0:
  print("best case")
else:
  print(list2[-1])
if len(list2)==len(list1):
  print("worst case")
else:
  print(list3[0])

```
