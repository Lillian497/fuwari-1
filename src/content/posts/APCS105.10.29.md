---
title: APCS 105年10月29日 程式設計實作題 
published: 2025-07-04
tags: [APCS考古題]
category: 程式解題日誌
draft: false
---
連結:https://apcs.csie.ntnu.edu.tw/wp-content/uploads/2018/12/1051029APCSImplementation.pdf
# 第1題  三角形辨別 
```markdown
from sys import stdin
date=list(map(int,stdin.readline().split()))
date.sort()
a,b,c=date[0],date[1],date[2]
print(*date)
if a+b<=c:
    print("No")
elif a*a+b*b<c*c:
    print("Obtuse")
elif a*a+b*b==c*c:
    print("Right")
elif a*a+b*b>c*c:
    print("Acute")


```
