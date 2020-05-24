---
layout: post
title:  "[프로그래머스] 전화번호 목록"
# subtitle: 
categories: algorithm
tags: 알고리즘 프로그래머스 Python3
comments: true
---

## 해시 - 전화번호 목록

* 문제 링크 : [전화번호 목록](https://programmers.co.kr/learn/courses/30/lessons/42577)

사용 언어 : Python3



```python
def solution(phone_book):
    answer = True
    
    phone_book = sorted(phone_book, key = lambda x : len(x))
    flag = 0
    while(phone_book) :
        temp = phone_book.pop(0)
        for i in phone_book :
            if temp in i[0:len(temp)] :
                answer = False
                flag = 1
                break
        if flag == 1 :
            break
    
    return answer
```