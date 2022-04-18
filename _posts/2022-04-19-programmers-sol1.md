---
layout: post
title:  "[프로그래머스] 신고 결과 받기"
# subtitle: 
categories: algorithm
tags: 알고리즘 프로그래머스 Python3
comments: true
# 공개여부:
published : true
---

## 2022 KAKAO BLIND RECRUITMENT - 신고 결과 받기

* 문제 링크 : [신고 결과 받기](https://programmers.co.kr/learn/courses/30/lessons/92334)

회사 생활중에 개발없는 인생에 현타를 느껴 다시 문제를 풀어가려고 한다.

deque써도 생각보다 시간이 오래걸리네 ㅠㅠ 열공해야겠다..

사용 언어 : Python3

```python
from collections import deque

def solution(id_list, report, k):
    answer = []
    
    report_dict = dict()
    report_dict_num = dict()
    reported_dict = dict()
    
    for id in id_list :
        report_dict_num[id] = 0
        reported_dict[id] = deque()
        report_dict[id] = deque()
        
    for id_target in report :
        id_nickname, id_target = id_target.split(' ')
        if id_target in report_dict[id_nickname] :
            continue
        else :
            report_dict[id_nickname].append(id_target)
        
        if id_nickname in reported_dict[id_target] :
            continue
        else :
            reported_dict[id_target].append(id_nickname)
            report_dict_num[id_target] += 1
    
    for id in id_list :
        num = 0
        for report_id in report_dict[id] :
            if report_dict_num[report_id] >= k :
                num += 1
        answer.append(num)
        
    return answer
```