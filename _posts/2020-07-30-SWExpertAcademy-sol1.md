---
layout: post
title:  "[SWEA] 1218. [S/W 문제해결 기본] 4일차 - 괄호 짝짓기"
# subtitle: 
categories: algorithm
tags: 알고리즘 SWEA Java
comments: true
# 공개여부:
published : true
---

## SW Expert Academy - 1218. [S/W 문제해결 기본] 4일차 - 괄호 짝짓기

사용 언어 : Java

```java
import java.util.Scanner;
import java.util.Stack;
 
class Solution
{
    public static void main(String args[]) throws Exception
    {
        Scanner sc = new Scanner(System.in);
        for(int test_case = 1; test_case <= 10; test_case++)
        {
            Stack<Character> stack = new Stack<>();
            int N = sc.nextInt();
             
            String s = sc.next();
            char temp = ' ';
            int flag = 0;
            for(int i=0; i<N; i++) {
                if(i==0) stack.push(s.charAt(i));
                else {
                    if(s.charAt(i) == ')') {
                        if(stack.isEmpty()) {flag = 1; break;}
                        else {
                            temp = stack.pop();
                            if(temp == '(') continue;
                            else {flag = 1; break;}
                        }
                    }
                    else if(s.charAt(i) == ']') {
                        if(stack.isEmpty()) {flag = 1; break;}
                        else {
                            temp = stack.pop();
                            if(temp == '[') continue;
                            else {flag = 1; break;}
                        }
                    }
                    else if(s.charAt(i) == '}') {
                        if(stack.isEmpty()) {flag = 1; break;}
                        else{
                            temp = stack.pop();
                            if(temp == '{') continue;
                            else {flag = 1; break;}
                        }   
                    }
                    else if(s.charAt(i) == '>') {
                        if(stack.isEmpty()) {flag = 1; break;}
                        else{
                            temp = stack.pop();
                            if(temp == '<') continue;
                            else {flag = 1; break;}
                        }   
                    }
                    else stack.push(s.charAt(i));
                }
            }
            System.out.print("#" + test_case + " ");
            if(flag==1) System.out.println(0);
            else System.out.println(1);    
             
            stack.clear();
        }
    }
}
```
