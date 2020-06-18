---
layout: post
title:  "[프로그래머스] 약수의 합"
# subtitle: 
categories: algorithm
tags: 알고리즘 프로그래머스 Python3 C++
comments: true
# 공개여부:
published : true
---

## 연습문제 - 약수의 합

* 문제 링크 : [약수의 합](https://programmers.co.kr/learn/courses/30/lessons/12928)

이런 쉬운 문제까지도 굳이 업로드 해야하나 싶기도하다.

사용 언어 : Python3

```python
def solution(n):
    answer = 0
    
    for i in range(1, n+1):
        if n % i == 0 :
            answer += i
    return answer
```

사용 연어 : C++

```cpp
#include <string>
#include <vector>

using namespace std;

int solution(int n) {
    int answer = 0;
    
    for(int i=1; i<=n; i++){
        if(n % i == 0)    answer+=i;
    }
    
    return answer;
}
```