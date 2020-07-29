---
layout: post
title:  "[SWEA] 2001. 파리 퇴치"
# subtitle: 
categories: algorithm
tags: 알고리즘 SWEA Java
comments: true
# 공개여부:
published : true
---

## SW Expert Academy - 2001. 파리 퇴치

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
        int[][] map = new int[15][15];
        for(int test_case = 1; test_case <= T; test_case++)
        {
            StringTokenizer st = new StringTokenizer(in.readLine());
            int N = Integer.parseInt(st.nextToken());
            int M = Integer.parseInt(st.nextToken());
             
            for(int y=0; y<N; y++) {
                st = new StringTokenizer(in.readLine());
                for(int x=0; x<N; x++) {
                    map[y][x] = Integer.parseInt(st.nextToken());
                }
            }
            int max = 0;
            for(int y=0; y<=N-M; y++) {
                for(int x=0; x<=N-M; x++) {
                    int count=0;
                    for(int my=0; my<M; my++) {
                        for(int mx=0; mx<M; mx++) {
                            count+=map[y+my][x+mx];
                        }
                    }
                    if(count>max) max=count;
                }
            }
            System.out.println("#" + test_case + " " + max);
        }
    }
}
```
