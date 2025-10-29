
# Desorting (800)

**Platform:** Codeforces  

**Author:** pratham15541  

**Submitted at:** 27/10/2025, 6:51:29 pm  

**Language:** Java 21  

**Verdict:** OK  

**Time:** 264 ms  

**Memory:** 1600.0 KB  

**Problem URL:** [https://codeforces.com/problemset/problem/1853/A](https://codeforces.com/problemset/problem/1853/A)  

**Submission URL:** [https://codeforces.com/contest/1853/submission/346022175](https://codeforces.com/contest/1853/submission/346022175)  

---

## Problem Statement
Call an array $a$ of length $n$ sorted if $a_1 \leq a_2 \leq \ldots \leq a_{n-1} \leq a_n$.

Ntarsis has an array $a$ of length $n$. 

He is allowed to perform one type of operation on it (zero or more times): 

 
*  Choose an index $i$ ($1 \leq i \leq n-1$). 
*  Add $1$ to $a_1, a_2, \ldots, a_i$. 
*  Subtract $1$ from $a_{i+1}, a_{i+2}, \ldots, a_n$. The values of $a$ can be negative after an operation.

Determine the minimum operations needed to make $a$ not sorted.

ExampleNoteIn the first case, we can perform $1$ operation to make the array not sorted: 

 
*  Pick $i = 1$. The array $a$ then becomes $[2, 0]$, which is not sorted. In the second case, we can perform $2$ operations to make the array not sorted: 

 
*  Pick $i = 3$. The array $a$ then becomes $[2, 9, 11, 12]$. 
*  Pick $i = 3$. The array $a$ then becomes $[3, 10, 12, 11]$, which is not sorted. It can be proven that $1$ and $2$ operations are the minimal numbers of operations in the first and second test cases, respectively.

In the third case, the array is already not sorted, so we perform $0$ operations.

### Sample Input
```
421 141 8 10 1331 3 231 9 14
```

### Sample Output
```
1
2
0
3
```

---

## Submitted Code

```java
/**
 * author:  Pratham Parikh
 * created: 27.10.2025 18:46:00 IST
**/
 
import java.io.*;
import java.util.*;
 
public class Main {
 
    private static void solve(FastScanner sc) throws Exception {
        int t = sc.nextInt();
        while (t-- > 0) {
            int n = sc.nextInt();
            int[] arr = new int[n];
            for(int i=0;i<n;i++){
                arr[i] = sc.nextInt();
            }
            int ans = 0;
            int min = Integer.MAX_VALUE;
            for(int i=1;i<n;i++){
                if(arr[i] >= arr[i-1]){
                    min = Math.min(min, arr[i] - arr[i-1]);
                    ans = (min/2)+1;
                }else{
                    ans = 0;
                    break;
                }
            }
 
            System.out.println(ans);
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
- greedy
- math
