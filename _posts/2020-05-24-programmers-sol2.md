---
layout: post
title:  "[프로그래머스] 힙"
# subtitle: 
categories: algorithm
tags: 알고리즘 프로그래머스 Python3
comments: true
---

## 힙(Heap) - 더 맵게

* 문제 링크 : [더 맵게](https://programmers.co.kr/learn/courses/30/lessons/42626)

사용 언어 : Python3

### 첫 번째 풀이

문제 분류 안보고 매 반복마다 sort해서 풀었더니 효율성이 전부 시간초과로 실패했다. 
이 경우 시간 복잡도는 O(N x Nlog(N))이 나온다. 힙 문제니까 얌전히 힙을 써서 풀어야겠다. 

힙에 대한 지식이 없다면 아래의 링크를 참고하자.

* 개념 링크 : [[개념정리] 힙(Heap)](https://https://bs-derek.github.io/algorithm/2020/05/24/algorithm-theory1)

```python
def solution(scoville, K):
    answer = 0
    while(True) :
        scoville = sorted(scoville)
        if scoville[0] >= K :
            break
        elif len(scoville) == 1 :
            answer = -1
            break
        else :
            first = scoville.pop(0)
            second = scoville.pop(0)

            scoville.append(first + (second * 2))
            answer+=1   
    return answer
```

### 두 번째 풀이

위의 코드를 그대로 힙으로 이식하면 효율성도 통과한다.

```python
import heapq
def solution(scoville, K):
    answer = 0
    heapq.heapify(scoville)
    
    while(True) :
        if scoville[0] >= K :
            break
        elif len(scoville) == 1 or len(scoville) == 0:
            answer = -1
            break
        else :
            first = heapq.heappop(scoville)
            second = heapq.heappop(scoville)
            heapq.heappush(scoville, first + (second*2))
            answer+=1
    return answer
```