---
layout: post
title:  "[SWEA] 1225. [S/W 문제해결 기본] 4일차 - 암호생성기"
# subtitle: 
categories: algorithm
tags: 알고리즘 SWEA Java
comments: true
# 공개여부:
published : true
---

## SW Expert Academy - 1225. [S/W 문제해결 기본] 4일차 - 암호생성기

사용 언어 : Java

```java
import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;
import java.util.ArrayDeque;
import java.util.Deque;
import java.util.StringTokenizer;
 
class Solution
{
    public static void main(String args[]) throws Exception
    {
    BufferedReader in = new BufferedReader(new InputStreamReader(System.in));
        Deque<Integer> dq = new ArrayDeque<Integer>();
         
        for(int test_case = 1; test_case <= 10; test_case++)
        {
            int T = Integer.parseInt(in.readLine());
            StringTokenizer st = new StringTokenizer(in.readLine());
             
            for(int i=0; i<8; i++) dq.add(Integer.parseInt(st.nextToken()));
             
            int count = 1;
            while(true) {
                int temp = dq.pollFirst();
                temp -= count;
                 
                if(temp <= 0) {
                    dq.addLast(0);
                    break;
                }
                else {
                    dq.addLast(temp);
                }
                 
                if(count == 5) count = 1;
                else count++;
                 
            }
            System.out.print("#" + test_case + " ");
            while(!dq.isEmpty()) {
                System.out.print(dq.pollFirst() + " ");
            }
            System.out.println();
             
            dq.clear();
        }
    }
}
```
