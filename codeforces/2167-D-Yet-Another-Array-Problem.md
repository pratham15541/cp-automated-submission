
# Yet Another Array Problem (Unrated)

**Platform:** Codeforces  

**Author:** pratham15541  

**Submitted at:** 28/10/2025, 9:06:40 pm  

**Language:** Java 21  

**Verdict:** OK  

**Time:** 296 ms  

**Memory:** 800.0 KB  

**Problem URL:** [https://codeforces.com/problemset/problem/2167/D](https://codeforces.com/problemset/problem/2167/D)  

**Submission URL:** [https://codeforces.com/contest/2167/submission/346292385](https://codeforces.com/contest/2167/submission/346292385)  

---

## Problem Statement
You are given an integer $n$ and an array $a$ of length $n$. 

Find the smallest integer $x$ ($2 \le x \le 10^{18}$) such that there exists an index $i$ ($1 \le i \le n$) with $\gcd$$^{\text{∗}}$(a_i, x) = 1$. If no such$x$exists within the range$[2,10^{18}]$, output$-1$.

$^{\text{∗}}$\gcd(x, y)$ denotes the greatest common divisor (GCD) of integers $x$ and $y$. 

ExampleNoteIn the first test case, $\gcd(2,1)=1$, which is the smallest number satisfying the condition.

In the second test case: 

 
*  $\gcd(2,6)=2$, $\gcd(2,12)=2$, so $2$ cannot be the answer. 
*  $\gcd(3,6)=3$, $\gcd(3,12)=3$, so $3$ cannot be the answer. 
*  $\gcd(4,6)=2$, $\gcd(4,12)=4$, so $4$ cannot be the answer. 
*  $\gcd(5,6)=1$, so the answer is $5$. In the third test case: 

 
*  $\gcd(2,24)=2$, $\gcd(2,120)=2$, $\gcd(2,210)=2$, so $2$ cannot be the answer. 
*  $\gcd(3,24)=3$, $\gcd(3,120)=3$, $\gcd(3,210)=3$, so $3$ cannot be the answer. 
*  $\gcd(4,24)=4$, $\gcd(4,120)=4$, $\gcd(4,210)=2$, so $4$ cannot be the answer. 
*  $\gcd(5,24)=1$, so the answer is $5$. In the fourth test case: 

 
*  $\gcd(2,2)=2$, $\gcd(2,4)=2$, $\gcd(2,6)=2$, $\gcd(2,10)=2$, so $2$ cannot be the answer. 
*  $\gcd(3,2)=1$, so the answer is $3$.

### Sample Input
```
4
1
1
4
6 6 12 12
3
24 120 210
4
2 4 6 10
```

### Sample Output
```
2
5
5
3
```

---

## Submitted Code

```java
/**
 * author:  Pratham Parikh
 * created: 28.10.2025 20:52:41 IST
**/
 
import java.io.*;
import java.util.*;
 
public class Main {
 
    private static void solve(FastScanner sc) throws Exception {
        int t = sc.nextInt();
        while (t-- > 0) {
            int n = sc.nextInt();
            long[] arr = new long[n];
            for (int i = 0; i < n; i++) {
                arr[i] = sc.nextLong();
            }
 
            long g = arr[0];
            for (int i = 1; i < n; i++) {
                g = gcd(g, arr[i]);
            }
 
            if (g == 1) {
                System.out.println(2);
            } else {
                long x = 2;
                while (x <= 1_000_000_000_000_000_000L && gcd(g, x) != 1) {
                    x++;
                }
                System.out.println(x > 1_000_000_000_000_000_000L ? -1 : x);
            }
        }
    }
 
    private static long gcd(long a, long b) {
        while (b != 0) {
            long tmp = a % b;
            a = b;
            b = tmp;
        }
        return a;
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
