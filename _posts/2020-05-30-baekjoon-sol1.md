---
layout: post
title:  "[백준] 15649번 - N과 M(1)"
# subtitle: 
categories: algorithm
tags: 알고리즘 백준 Python3
comments: true
# 공개여부:
published : true
---

## 15649번 - N과 M(1)

* 문제 링크 : [N과 M(1)](https://www.acmicpc.net/problem/15649)

사용 언어 : Python3

DFS를 이용한 재귀함수 다시 공부할겸, 순열과 조합 라이브러리 사용할 겸 다시 풀어보는 N과 M시리즈

### 첫 번째 풀이(python 라이브러리 사용)

```python
import sys
import itertools

N, M = map(int, sys.stdin.readline().split())

for i in itertools.permutations([j for j in range(1, N+1)], M):
    print(str(i)[1:-1].replace(',', ''))
```

### 두 번째 풀이(DFS구현)

효율성 높여보겠다고 deque 쓰고 sys.stdin 썼는데, 우째서 예전 코드보다 메모리랑 시간 둘 다 많이 쓴 거지..?


```python
import sys
from collections import deque

N, M = map(int, sys.stdin.readline().split())
temp = deque()
isVisited = [0] * N

def dfs(start):
    if start == M:
        print (*temp)
        return

    for i in range(0, N) :
        if isVisited[i] == True :
            continue
        isVisited[i] = True
        temp.append(i+1)
        dfs(start+1)
        temp.pop()
        isVisited[i] = 0

dfs(0)
```