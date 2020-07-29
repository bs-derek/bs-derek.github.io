---
layout: post
title:  "[SWEA] 1873. 상호의 배틀필드"
# subtitle: 
categories: algorithm
tags: 알고리즘 SWEA Java
comments: true
# 공개여부:
published : true
---

## SW Expert Academy - 1873. 상호의 배틀필드

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
        for(int test_case = 1; test_case <= T; test_case++)
        {
            StringTokenizer st = new StringTokenizer(in.readLine());
            String a = st.nextToken();
            String b = st.nextToken();
            if(a.length() != b.length()) {
                System.out.print("#" + test_case + " ");
                System.out.println("DIFF");
                continue;
            }
            else {
                int flag = 0;
                for(int i=0; i<a.length(); i++) {
                    if(a.charAt(i) == 'C' || a.charAt(i) == 'E' || a.charAt(i) == 'F' ||
                            a.charAt(i) == 'G' || a.charAt(i) == 'H' || a.charAt(i) == 'I' ||
                            a.charAt(i) == 'J' || a.charAt(i) == 'K' || a.charAt(i) == 'L' ||
                            a.charAt(i) == 'M' || a.charAt(i) == 'N' || a.charAt(i) == 'S' ||
                            a.charAt(i) == 'T' || a.charAt(i) == 'U' || a.charAt(i) == 'V' ||
                            a.charAt(i) == 'W' || a.charAt(i) == 'X' || a.charAt(i) == 'Y' ||
                            a.charAt(i) == 'Z') {
                        if(b.charAt(i) == 'C' || b.charAt(i) == 'E' || b.charAt(i) == 'F' ||
                            b.charAt(i) == 'G' || b.charAt(i) == 'H' || b.charAt(i) == 'I' ||
                            b.charAt(i) == 'J' || b.charAt(i) == 'K' || b.charAt(i) == 'L' ||
                            b.charAt(i) == 'M' || b.charAt(i) == 'N' || b.charAt(i) == 'S' ||
                            b.charAt(i) == 'T' || b.charAt(i) == 'U' || b.charAt(i) == 'V' ||
                            b.charAt(i) == 'W' || b.charAt(i) == 'X' || b.charAt(i) == 'Y' ||
                            b.charAt(i) == 'Z') continue;
                        else {flag = 1; break;}
                    }
                    else if(a.charAt(i) == 'A' || a.charAt(i) == 'D' || a.charAt(i) == 'O' ||
                            a.charAt(i) == 'P' || a.charAt(i) == 'Q' || a.charAt(i) == 'R') {
                        if(b.charAt(i) == 'A' || b.charAt(i) == 'D' || b.charAt(i) == 'O' ||
                            b.charAt(i) == 'P' || b.charAt(i) == 'Q' || b.charAt(i) == 'R') continue;
                        else {flag = 1; break;}
                    }
                    else {
                        if(b.charAt(i) == a.charAt(i)) continue;
                        else {flag = 1; break;}
                    }
                }
                 
                System.out.print("#" + test_case + " ");
                if(flag == 0) System.out.println("SAME");
                else System.out.println("DIFF");
            }
         
        }       
    }
}
```
