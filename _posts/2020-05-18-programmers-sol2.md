---
layout: post
title:  "[프로그래머스] 완주하지 못한 선수"
# subtitle: 
categories: algorithm
tags: 알고리즘 프로그래머스 Python3
comments: true
# 공개여부:
published : true
---

## 해시 - 완주하지 못한 선수

* 문제 링크 : [완주하지 못한 선수](https://programmers.co.kr/learn/courses/30/lessons/42576)

사용 언어 : Python3

### 첫 번째 풀이 (실패)

강려크한 파이썬느님은 Set(집합)을 구현해놔서 간단하게 차집합으로 연산하려고 했더니 역시 테케 3번째에 중복의 경우를 집어넣어 놨다. 그래서 하나씩 빼고 in을 이용해서 했더니 정확성은 통과했고, 효율성은 모두 시간 초과  
이보다 어떻게 효율이 더 좋지? 생각했는데 remove 함수가 문제인 것 같다.

```python
def solution(bridge_length, weight, truck_weights):
    def solution(participant, completion):
    answer=''
    while (True) :
        temp = participant.pop()
        if completion == False :
            answer += temp
            break
        elif temp in completion :
            completion.remove(temp)
        else :
            answer += temp
            break
    return answer
```

### 두 번째 풀이(통과)

remove 함수가 문제가 맞다. 각각의 배열을 정렬해주고 비교하면서 풀어준 결과 효율성도 통과

```python
def solution(participant, completion):
    answer=''

    participant = sorted(participant)
    completion = sorted(completion)
    temp = len(completion)

    for i in range(temp+1) :
        if i == temp :
            answer += participant[i]
            break
        elif participant[i] != completion[i] :
            answer+=participant[i]
            break

    return answer
```