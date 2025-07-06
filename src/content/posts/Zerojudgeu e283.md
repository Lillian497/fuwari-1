---
title: Zerojudgeu e283. APCS 類似題 - 小崴的特殊編碼
published: 2025-07-06
tags: [Zerojudgeu]
category: 程式解題日誌
draft: false
---

連結:https://zerojudge.tw/ShowProblem?problemid=e283
#  Zerojudgeu e283. APCS 類似題 - 小崴的特殊編碼
```python
from sys import stdin
for n in stdin:
    n=int(n)
    date=[(stdin.readline().strip()) for _ in range(n)]
    string=""

    for u in date:
        if u=="0 1 0 1":
            string+="A"
        elif u=="0 1 1 1":
            string+="B"
        elif u=="0 0 1 0":
            string+="C"
        elif u=="1 1 0 1":
            string+="D"
        elif u=="1 0 0 0":
            string+="E"
        else:
            string+="F"

    print(string)

```
