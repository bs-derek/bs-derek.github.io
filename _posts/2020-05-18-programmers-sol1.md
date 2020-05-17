---
layout: post
title:  "[프로그래머스] 다리를 지나는 트럭"
# subtitle: 
categories: algorithm
tags: 알고리즘 프로그래머스 Python3
comments: true
---

## 스택/큐 - 다리를 지나는 트럭

* 문제 링크 : [다리를 지나는 트럭](https://programmers.co.kr/learn/courses/30/lessons/42583?language=python3#)

사용 언어 : Python3

#### 첫 번째 풀이

오늘 집중을 못해서 그런가,, 되게 오랫동안 붙잡고 있었다.  
일단은 처음 푼 코드는 다음과 같다. 테스트 5에서 시간 초과로 실패가 나온다. 아무래도 sum 함수를 남발해서 그런 것 같다.

```python
def solution(bridge_length, weight, truck_weights):
    answer = 0
    bridge_state = [0 for i in range(bridge_length)]
    current = truck_weights.pop(0)
    while(True) :

        if sum(bridge_state) == 0 and len(truck_weights) == 0 and answer > 0:
            break
        answer += 1
        if sum(bridge_state) + current > weight and current!=0:
            bridge_state.insert(0, 0)
            bridge_state.pop()
            if sum(bridge_state) == 0 or sum(bridge_state) + current <=weight:
                bridge_state[0] = current
                if len(truck_weights) > 0 and current!=0 :
                    current = truck_weights.pop(0)
                else :
                    current = 0
        else:
            bridge_state.insert(0, current)
            bridge_state.pop()
            if len(truck_weights) > 0 and current!=0 :
                current = truck_weights.pop(0)
            else :
                current = 0
    return answer
```

#### 두 번째 풀이

sum 함수를 없애고 배열에서 들어가고 빠질 때 마다 sum을 직접 계산해서 갱신해주니 효율성이 훨씬 좋아졌다. 하지만, 코드가 많이 더러운 것 같다. 다시 풀때는 좀더 간결하게 풀어봐야겠다.

```python
def solution(bridge_length, weight, truck_weights):
    answer = 0
    bridge_state = [0 for i in range(bridge_length)]
    bridge_sum = 0
    current = truck_weights.pop(0)
    while(True) :

        if bridge_sum == 0 and len(truck_weights) == 0 and answer > 0:
            break
        answer += 1
        if bridge_sum + current > weight and current!=0:
            bridge_state.insert(0, 0)
            temp = bridge_state.pop()
            if temp != 0 :
                bridge_sum -= temp
            if bridge_sum == 0 or bridge_sum + current <=weight:
                bridge_state[0] = current
                bridge_sum += current
                if len(truck_weights) > 0 and current!=0 :
                    current = truck_weights.pop(0)
                else :
                    current = 0
        else:
            bridge_state.insert(0, current)
            bridge_sum += current
            temp = bridge_state.pop()
            if temp != 0 :
                bridge_sum -= temp
            if len(truck_weights) > 0 and current!=0 :
                current = truck_weights.pop(0)
            else :
                current = 0
    return answer
```