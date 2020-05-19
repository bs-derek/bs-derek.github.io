---
layout: post
title:  "[프로그래머스] 가장 큰 수"
# subtitle: 
categories: algorithm
tags: 알고리즘 프로그래머스 Python3
comments: true
---

## 정렬 - 가장 큰 수

* 문제 링크 : [가장 큰 수](https://programmers.co.kr/learn/courses/30/lessons/42746#)

사용 언어 : Python3

### 첫 번째 풀이

sorted 함수를 사용하여 key값을 맨 앞자리로 정렬해서 풀려고 했는데 틀렸다. 왜냐하면 [3, 35, 34, 331, 30, 5, 9]
라는 배열을 정렬하면 [9, 5, 3, 35, 34, 331, 30]으로 정렬되기 때문이다. 331뒤에 3이 들어가야 하는데 이 부분을 캐치하지 못한다.

```python
def solution(numbers):
    answer = ''
    
    numbers = sorted(numbers, key=lambda x:str(x)[0], reverse = True)
    numbers = map(str, numbers)
    answer = ''.join(numbers)
    return answer
```

### 두 번째 풀이

```python

```