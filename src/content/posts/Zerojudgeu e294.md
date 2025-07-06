---
title: Zerojudgeu e294. 類似題 - 小崴的新發現
published: 2025-07-06
tags: [Zerojudgeu]
category: 程式解題日誌
draft: false
---

連結:https://zerojudge.tw/ShowProblem?problemid=e294
#  Zerojudgeu e294. APCS 類似題 - 小崴的新發現
```python
def small(i):
    i=i.copy()
    c=-1
    
    for t in i:
        c+=1
        if t==0:
            if i[c-1]==1:
              i[c-1]-=1
              for o in range(len(i)-c):
                  i[c]=9
                  c+=1
              break
            else:
              return False
        
        if t%2==0:
            i[c]-=1  
            for o in range(len(i)-c-1):
                c+=1
                i[c]=9
            break
    i=''.join(map(str,i))
    i=int(i)
    return i

def big(i):
    i=i.copy()
    c=-1
    for t in i:
        c+=1
        if t%2==0:
            i[c]+=1
            for o in range(len(i)-c-1):
                c+=1
                i[c]=1

            break
    i=''.join(map(str,i))
    i=int(i)
    return i
try:
    while True:
        i=int(input())
        i=list(map(int,str(i)))
        p=len(i)
        y=small(i)
        x=big(i)
        i=''.join(map(str,i))
        i=int(i)
        if i==0:
            print(1)
        elif i-y>x-i or y==False:
            print(x-i)
        else:
            print(i-y)
except EOFError:
    pass
```
