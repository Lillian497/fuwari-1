---
title: Zerojudgeu e289. 美麗的彩帶
published: 2025-07-06
tags: [Zerojudgeu]
category: 程式解題日誌
draft: false
---

連結:https://zerojudge.tw/ShowProblem?problemid=e289
#  Zerojudgeu e289. 美麗的彩帶
```python
def add(next_num,color,dic):
    if color[next_num] in dic:
        dic[color[next_num]]+=1
    else:
        dic[color[next_num]]=1

##next_num=0
##color=[1]
##dic1={1:1,2:1,3:1}##有一個
##dic2={1:2,2:1}##有二個
##dic3={1:3}##有三個
##dic4={2:2,3:1}##無
##
##dic=dic4
##
##
##add(next_num,color,dic)
##print(dic)
    
def cup(first_num,color,dic):
    dic[color[first_num]]-=1
    if dic[color[first_num]]==0:
        dic.pop(color[first_num])
##first_num=0
##color=[1]
##dic1={1:1,2:1,3:1}##有一個
##dic2={1:2,2:1}##有二個
##dic3={1:3}##有三個
##dic4={1:4}##有4個
##
##dic=dic4
##cup(first_num,color,dic)
##print(dic)
        
##m1=3
##n1=7
##color1=[1,2,3,5,4,5,4]
##
##m2=2
##n2=7
##color2=[1,2,2,1,2,1,2]
##
##n=n2
##m=m2
##color=color2


from sys import stdin

m,n=map(int,stdin.readline().split())
color=list(map(int,stdin.readline().split()))
ans=0
dic=dict()
for t in range(m):
    dic[color[t]]=1
if len(dic)==m:
    ans+=1
##print(dic)   

for i in range(len(color)-m):
    add(i+m,color,dic)
    cup(i,color,dic)
##    print(dic)
    if len(dic)==m:
        ans+=1
print(ans)
    

```
