
# Serval and Mocha's Array (800)

**Platform:** Codeforces  

**Author:** pratham15541  

**Submitted at:** 10/31/2025, 9:26:24 AM  

**Language:** Java 21  

**Verdict:** OK  

**Time:** 452 ms  

**Memory:** 800.0 KB  

**Problem URL:** [https://codeforces.com/problemset/problem/1789/A](https://codeforces.com/problemset/problem/1789/A)  

**Submission URL:** [https://codeforces.com/contest/1789/submission/346797158](https://codeforces.com/contest/1789/submission/346797158)  

---

## Problem Statement
Mocha likes arrays, and Serval gave her an array consisting of positive integers as a gift.

Mocha thinks that for an array of positive integers $a$, it is good iff the greatest common divisor of all the elements in $a$ is no more than its length. And for an array of at least $2$ positive integers, it is beautiful iff all of its prefixes whose length is no less than $2$ are good. 

For example:

 
*  $[3,6]$ is not good, because $\gcd(3,6)=3$ is greater than its length $2$. 
*  $[1,2,4]$ is both good and beautiful, because all of its prefixes whose length is no less than $2$, which are $[1,2]$ and $[1,2,4]$, are both good. 
*  $[3,6,1]$ is good but not beautiful, because $[3,6]$ is not good. Now Mocha gives you the gift array $a$ of $n$ positive integers, and she wants to know whether array $a$ could become beautiful by reordering the elements in $a$. It is allowed to keep the array $a$ unchanged.

ExampleNoteIn the first test case, neither $[3,6]$ nor $[6,3]$ are beautiful, so it's impossible to obtain a beautiful array by reordering the elements in $a$.

In the second test case, $[1,2,4]$ is already beautiful. Keeping the array $a$ unchanged can obtain a beautiful array.

### Sample Input
```
6
2
3 6
3
1 2 4
3
3 6 1
3
15 35 21
4
35 10 35 14
5
1261 227821 143 4171 1941
```

### Sample Output
```
No
Yes
Yes
No
Yes
Yes
```

---

## Submitted Code

```java
/**
 * author:  Pratham Parikh
 * created: 31.10.2025 14:28:50 IST
**/
 
import java.io.*;
import java.util.*;
 
public class Main {
 
    private static int gcd(int a, int b){
        if(b==0) return a;
        return gcd(b,a%b);
    }
    private static void solve(FastScanner sc) throws Exception {
        int t = sc.nextInt();
        while (t-- > 0) {
            int n = sc.nextInt();
            int[] arr = new int[n];
            for(int i=0;i<n;i++){
                arr[i] = sc.nextInt();
            }        
            Arrays.sort(arr);    
 
            boolean flag = false;
            for(int i=0;i<n;i++){
                for(int j=i+1;j<n;j++){
                    if(gcd(arr[i],arr[j]) <=2){
                        flag = true;
                        break;
                    }
                }
            }
 
            System.out.println(flag ? "Yes" : "No");
        }
    }
 
    public static void main(String[] args) {
        try {
            FastScanner sc = new FastScanner();
            solve(sc);
        } catch (Exception e) {
            e.printStackTrace();
        }
 
    }
 
    // ======== FastScanner ========
    static class FastScanner {
        private final InputStream in;
        private final byte[] buffer = new byte[1 << 16]; // 64 KB buffer
        private int ptr = 0, len = 0;
 
        FastScanner() {
            in = System.in;
        }
 
        private int readByte() throws IOException {
            if (ptr >= len) {
                ptr = 0;
                len = in.read(buffer);
                if (len <= 0)
                    return -1;
            }
            return buffer[ptr++];
        }
 
        String next() throws IOException {
            StringBuilder sb = new StringBuilder();
            int c;
            while ((c = readByte()) != -1 && c <= ' ')
                ; // skip spaces
            while (c != -1 && c > ' ') {
                sb.append((char) c);
                c = readByte();
            }
            return sb.toString();
        }
 
        int nextInt() throws IOException {
            int c = readByte();
            while (c <= ' ')
                c = readByte();
            int sign = 1;
            if (c == '-') {
                sign = -1;
                c = readByte();
            }
            int val = 0;
            while (c >= '0' && c <= '9') {
                val = val * 10 + (c - '0');
                c = readByte();
            }
            return val * sign;
        }
 
        long nextLong() throws IOException {
            int c = readByte();
            while (c <= ' ')
                c = readByte();
            int sign = 1;
            if (c == '-') {
                sign = -1;
                c = readByte();
            }
            long val = 0;
            while (c >= '0' && c <= '9') {
                val = val * 10 + (c - '0');
                c = readByte();
            }
            return val * sign;
        }
 
        double nextDouble() throws IOException {
            return Double.parseDouble(next());
        }
 
        String nextLine() throws IOException {
            StringBuilder sb = new StringBuilder();
            int c = readByte();
            while (c == '\r' || c == '\n')
                c = readByte(); // skip line breaks
            while (c != -1 && c != '\n' && c != '\r') {
                sb.append((char) c);
                c = readByte();
            }
            return sb.toString();
        }
    }
}
```

---

## Problem Tags
- brute force
- math
- number theory
