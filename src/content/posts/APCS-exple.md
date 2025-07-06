---
title: APCS  題目範例 秘密差 程式設計實作題 
published: 2025-07-06
tags: [APCS考古題]
category: 程式解題日誌
draft: false
---

連結:https://apcs.csie.ntnu.edu.tw/index.php/questionstypes/previousexam/
#  題目範例 秘密差
```python
X=input()
list1=list(X)
a=0
b=0
for i in range(len(list1)-1,-1,-1):
    if i%2==0:
        b+=int(list1[i])
    else:
        a+=int(list1[i])
j=a-b
if j<0:
    print(-j,"\n")
else:
    print(j,"\n")

```

