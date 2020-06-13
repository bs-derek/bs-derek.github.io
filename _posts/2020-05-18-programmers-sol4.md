---
layout: post
title:  "[프로그래머스] 모의고사"
# subtitle: 
categories: algorithm
tags: 알고리즘 프로그래머스 Python3
comments: true
# 공개여부:
published : true
---

## 완전탐색 - 모의고사

* 문제 링크 : [모의고사](https://programmers.co.kr/learn/courses/30/lessons/42840)

사용 언어 : Python3

그렇게 어려운 건 없다. 반복되는 숫자가 같으니 나머지 연산자(%)로 반복문 해결하고, 기억해놔야 할 것은 enumerate 사용  
내가 쓴 방식은 index 여러 개를 가져올 때 사용하는 것이다.

```python
def solution(answers):
    first = [1,2,3,4,5]
    second = [2,1,2,3,2,4,2,5]
    third = [3,3,1,1,2,2,4,4,5,5]
    first_score = 0
    second_score = 0
    third_score = 0
    for i in range(len(answers)):
        if answers[i] == first[i%5] :
            first_score += 1
        if answers[i] == second[i%8] :
            second_score += 1
        if answers[i] == third[i%10] :
            third_score += 1
    
    temp = [first_score, second_score, third_score]
    answer = [i+1 for i, value in enumerate(temp) if value == max(temp)]
    return answer
```