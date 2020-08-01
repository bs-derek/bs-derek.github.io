---
layout: post
title:  "[SWEA] 3499. 퍼펙트 셔플"
# subtitle: 
categories: algorithm
tags: 알고리즘 SWEA Java
comments: true
# 공개여부:
published : true
---

## SW Expert Academy - 3499. 퍼펙트 셔플

사용 언어 : Java

```java
import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;
import java.util.StringTokenizer;
 
class Solution
{
    public static void main(String args[]) throws Exception
    {
        BufferedReader in = new BufferedReader(new InputStreamReader(System.in));
         
        int T = Integer.parseInt(in.readLine());
        String[] s1 = new String[500];
        String[] s2 = new String[500];
        for(int test_case = 1; test_case<=T; test_case++) {
            int N = Integer.parseInt(in.readLine());
            int s1_cnt = 0, s2_cnt = 0;
            StringTokenizer st = new StringTokenizer(in.readLine());
            if(N%2 == 1) {
                for(int i=0; i<N/2; i++) s1[s1_cnt++] = st.nextToken();
                s1[s1_cnt++] = st.nextToken();
                for(int i=0; i<N/2; i++) s2[s2_cnt++] = st.nextToken();
            }
            else {
                for(int i=0; i<N/2; i++) s1[s1_cnt++] = st.nextToken();
                for(int i=0; i<N/2; i++) s2[s2_cnt++] = st.nextToken();
            }
             
            System.out.print("#" + test_case + " ");
            if(s1_cnt == s2_cnt) {
                for(int i=0; i<s1_cnt; i++) System.out.print(s1[i] + " " + s2[i] + " ");
                System.out.println();
            }
            else {
                for(int i=0; i<s2_cnt; i++) System.out.print(s1[i] + " " + s2[i] + " ");
                System.out.println(s1[s1_cnt-1]);
            }
        }
    }
}
```
