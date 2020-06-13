---
layout: post
title:  "[프로그래머스] 조이스틱"
# subtitle: 
categories: algorithm
tags: 알고리즘 프로그래머스 Python3
comments: true
# 공개여부:
published : true
---

## 탐욕법(Greedy) - 조이스틱

* 문제 링크 : [조이스틱](https://programmers.co.kr/learn/courses/30/lessons/42860#)

사용 언어 : Python3

### 첫 번째 풀이

아.. 이거 왜 레벨 1, 2에 섞여있냐..  
특정 케이스를 생각하지 못하면 되게 시간이 많이 걸리니까 주의하자...
현재 커서위치(pos) 기준으로 'A'가 아닌 문자열이 왼쪽에 가까이 있는 경우와 오른쪽에
가까이 있는 경우를 나눠서 가장 가까운 쪽으로 가게했다. 이렇게 하면 큰 시간낭비가 된다.

name = "AABAAAAAAABBB" 인 경우를 생각해보면 최소값은 3번째 있는 B값을 먼저 바꿔야 11이다. 하지만, 내 코드로 돌려보면 3번째 B를 향해 가는 거리(2)보다 마지막에 있는 B를 향해 가는 거리(1)이 더 작으므로 왼쪽으로 움직이다보니 12가 나오게 된다.. 부들부들..


```python
def solution(name):
    answer = 0
    pos = 0
    currentName = 'A' * len(name)
    direction = 0

    while(currentName != name) :
        if currentName[pos] == name[pos]:
            right = 1
            left = 1
            for i in range(1, len(name)) :
                if name[pos+i] != 'A':
                    break
                else :
                    right+=1
            for i in range(1, len(name)) :
                if name[pos-i] != 'A' and currentName[pos-i] != name[pos-i]:
                    break
                else :
                    left+=1
            if right < left :
                pos += right
                answer += right
                direction = 1
            elif right == left:
                if direction >= 0 :
                    pos += right
                    answer += right
                else :
                    pos -= left
                    answer+=left
            else:
                pos -= left
                answer += left
                direction = -1
        else :
            if abs(ord(name[pos]) - ord('A')) < abs(ord('Z') - ord(name[pos])) :
                answer += abs(ord(name[pos]) - ord('A'))
                temp = list(currentName)
                temp[pos] = name[pos]
                currentName = ''.join(temp)
            else :
                answer += abs(ord('Z') - ord(name[pos])+1)
                temp = list(currentName)
                temp[pos] = name[pos]
                currentName = ''.join(temp)
    return answer
```

### 두 번째 풀이

그거 때문에 틀린게 아니라 오른쪽을 향해 갈 때 조건을 하나 빼먹었더니 다른 케이스에서 틀린거란다. 문제 자체가 Greedy이기 때문에 최적해를 찾을 수 없어 위에서 설명한 경우는 12가 나오는게 맞다고 한다. 문제에 써놓든가..

```python
def solution(name):
    answer = 0
    pos = 0
    currentName = 'A' * len(name)
    direction = 0

    while(currentName != name) :
        if currentName[pos] == name[pos]:
            right = 1
            left = 1
            for i in range(1, len(name)) :
                if name[pos+i] != 'A' and currentName[pos+i] != name[pos+i]:
                    break
                else :
                    right+=1
            for i in range(1, len(name)) :
                if name[pos-i] != 'A' and currentName[pos-i] != name[pos-i]:
                    break
                else :
                    left+=1
            if right < left :
                pos += right
                answer += right
                direction = 1
            elif right == left:
                if direction >= 0 :
                    pos += right
                    answer += right
                else :
                    pos -= left
                    answer+=left
            else:
                pos -= left
                answer += left
                direction = -1
        else :
            if abs(ord(name[pos]) - ord('A')) < abs(ord('Z') - ord(name[pos])) :
                answer += abs(ord(name[pos]) - ord('A'))
                temp = list(currentName)
                temp[pos] = name[pos]
                currentName = ''.join(temp)
            else :
                answer += abs(ord('Z') - ord(name[pos])+1)
                temp = list(currentName)
                temp[pos] = name[pos]
                currentName = ''.join(temp)
    return answer
```