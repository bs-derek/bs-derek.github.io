---
layout: post
title:  "[SWEA] 1208. [S/W 문제해결 기본] 1일차 - Flatten"
# subtitle: 
categories: algorithm
tags: 알고리즘 SWEA Java
comments: true
# 공개여부:
published : true
---

## SW Expert Academy - 1208. [S/W 문제해결 기본] 1일차 - Flatten

사용 언어 : Java

```java
import java.util.Scanner;
import java.util.Arrays;
 
class Solution
{
    public static void main(String args[]) throws Exception
    {
        Scanner sc = new Scanner(System.in);
        int i=0;
        int[] arr = new int[100];
        for(int test_case = 1; test_case <= 10; test_case++)
        {
            int dump = sc.nextInt();
             
            for(i=0; i<100; i++) {
                arr[i] = sc.nextInt();
            }
            Arrays.sort(arr);
             
            for(i=0; i<dump; i++) {
                if(arr[99] == arr[0]) break;
                arr[99]--;
                arr[0]++;
                Arrays.sort(arr);
            }
             
            System.out.println("#" + test_case + " " + (arr[99] - arr[0]));
        }
        sc.close();
    }
}
```