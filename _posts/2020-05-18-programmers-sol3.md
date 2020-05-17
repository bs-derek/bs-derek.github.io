---
layout: post
title:  "[프로그래머스] 문자열 압축"
# subtitle: 
categories: algorithm
tags: 알고리즘 프로그래머스 Python3
comments: true
---

## 2020 KAKAO BLIND RECRUITMENT - 문자열 압축

* 문제 링크 : [문자열 압축](https://programmers.co.kr/learn/courses/30/lessons/60057)

사용 언어 : Python3


파이썬은 문자열 쉽다던데 난 왜이러냐

```python
import copy

def solution(s):
    length = []
    length.append(len(s))
    for i in range(1, int(len(s)/2)+1) :
        new_s = copy.deepcopy(s)
        count = 1
        previous_str = new_s[0:i]
        new_s = new_s.replace(previous_str,"",1)
        new_str = ''
        flag = 0
        while(True) :
            current_str = new_s[0:i]
            if current_str == previous_str and flag!=1 :
                count+=1
                new_s = new_s.replace(current_str,"",1)
                previous_str = current_str
            else :
                if count!= 1:
                    new_str+=str(count)
                new_str+=previous_str
                previous_str=current_str
                count=1
                new_s = new_s.replace(current_str,"",1)
                if flag == 1:
                    break
                if len(new_s) == 0 :
                    flag = 1
        length.append(len(new_str))
    return min(length)
```