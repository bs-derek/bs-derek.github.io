---
layout: post
title:  "[프로그래머스] 쇠막대기"
# subtitle: 
categories: algorithm
tags: 알고리즘 프로그래머스 Python3
comments: true
# 공개여부:
published : true
---

## 스택/큐 - 쇠막대기

* 문제 링크 : [쇠막대기](https://programmers.co.kr/learn/courses/30/lessons/42585)

사용 언어 : Python3

```python
def solution(arrangement):
    tmp = []
    answer = 0
    for i in range(len(arrangement)) :
        if(arrangement[i] == '(') :
            tmp.append(1)
        else:
            tmp.pop()
            if arrangement[i-1]=='(' :
                answer += len(tmp)
            else :
                answer+=1
    print(answer)
    
    return answer
```