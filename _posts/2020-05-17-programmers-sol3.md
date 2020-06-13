---
layout: post
title:  "[프로그래머스] 스킬트리"
# subtitle: 
categories: algorithm
tags: 알고리즘 프로그래머스 Python3
comments: true
# 공개여부:
published : true
---

## Summer/Winter Coding(~2018) - 스킬트리

* 문제 링크 : [스킬트리](https://programmers.co.kr/learn/courses/30/lessons/49993?language=python3)

사용 언어 : Python3

이 문제는 python의 replace 함수를 이용하면 정말 간단히 풀 수 있다..

```python
import copy

def solution(skill, skill_trees):
    answer = len(skill_trees)
    impossible = 0
    
    for i in skill_trees:
        skill_copy = copy.deepcopy(skill)
        for j in i:
            if j in skill_copy :
                if j == skill_copy[0] :
                    skill_copy = skill_copy.replace(j, "")
                else :
                    impossible += 1
                    break
            else :
                continue
    return answer - impossible
```