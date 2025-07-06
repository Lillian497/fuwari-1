---
title: Zerojudgeu e286. 籃球比賽
published: 2025-07-06
tags: [Zerojudgeu]
category: 程式解題日誌
draft: false
---

連結:https://zerojudge.tw/ShowProblem?problemid=e286
#  Zerojudgeu e286. 籃球比賽
```python
list1=map(int,input().split())
list2=map(int,input().split())
list12=map(int,input().split())
list22=map(int,input().split())
m=sum(list1)
o=sum(list12)
n=sum(list2)
l=sum(list22)
me=0
you=0
print(f"{m}:{n}")      
print(f"{o}:{l}")
if m>n:
    me+=1
if n>m:
    you+=1
if o>l:
    me+=1
if l>o:
    you+=1
if me>you:
    print("Win")
elif you>me:
    print("Lose")
else:
    print("Tie")

```
