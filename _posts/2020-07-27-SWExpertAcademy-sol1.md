---
layout: post
title:  "[SWEA] 1289. 원재의 메모리 복구하기"
# subtitle: 
categories: algorithm
tags: 알고리즘 SWEA Java
comments: true
# 공개여부:
published : true
---

## SW Expert Academy - 1289. 원재의 메모리 복구하기

최근에 SSAFY과정 때문에 사용 언어가 Java로 올라가게 될 예정이다..

사용 언어 : Java

```Java
import java.util.Scanner;
 
class Solution
{
    public static void main(String args[]) throws Exception
    {
        Scanner sc = new Scanner(System.in);
        int T;
        T=sc.nextInt();
        sc.nextLine();
        for(int test_case = 1; test_case <= T; test_case++)
        {
            String bits = sc.nextLine();
            int flag = 0;
            int count = 0;
            for(int i=0; i<bits.length(); i++){
                if(flag == 0 && bits.charAt(i)== '0') continue;
                else if(flag == 1 && bits.charAt(i)== '1') continue;
                else if(flag == 1 && bits.charAt(i)== '0') {count++; flag=0;}
                else if(flag == 0 && bits.charAt(i)== '1') {count++; flag=1;}
            }
            System.out.println("#" + test_case + " " + count);
        }
    }
}
```