
# Unit Array (800)

**Platform:** Codeforces  

**Author:** pratham15541  

**Submitted at:** 27/10/2025, 11:11:20 pm  

**Language:** Java 21  

**Verdict:** OK  

**Time:** 234 ms  

**Memory:** 600.0 KB  

**Problem URL:** [https://codeforces.com/problemset/problem/1834/A](https://codeforces.com/problemset/problem/1834/A)  

**Submission URL:** [https://codeforces.com/contest/1834/submission/346063706](https://codeforces.com/contest/1834/submission/346063706)  

---

## Problem Statement
Given an array $a$ of length $n$, which elements are equal to $-1$ and $1$. Let's call the array $a$ good if the following conditions are held at the same time:

 
*  $a_1 + a_2 + \ldots + a_n \ge 0$; 

*  $a_1 \cdot a_2 \cdot \ldots \cdot a_n = 1$. In one operation, you can select an arbitrary element of the array $a_i$ and change its value to the opposite. In other words, if $a_i = -1$, you can assign the value to $a_i := 1$, and if $a_i = 1$, then assign the value to $a_i := -1$.

Determine the minimum number of operations you need to perform to make the array $a$ good. It can be shown that this is always possible.

ExampleNoteIn the first test case, we can assign the value $a_1 := 1$. Then $a_1 + a_2 + a_3 + a_4 = 1 + (-1) + 1 + (-1) = 0 \ge 0$ and $a_1 \cdot a_2 \cdot a_3 \cdot a_4 = 1 \cdot (-1) \cdot 1 \cdot (-1) = 1$. Thus, we performed $1$ operation.

In the second test case, we can assign $a_1 := 1$. Then $a_1 + a_2 + a_3 + a_4 + a_5 = 1 + (-1) + (-1) + 1 + 1 = 1 \ge 0$ and $a_1 \cdot a_2 \cdot a_3 \cdot a_4 \cdot a_5 = 1 \cdot (-1) \cdot (-1) \cdot 1 \cdot 1 = 1$. Thus, we performed $1$ operation.

In the third test case, $a_1 + a_2 + a_3 + a_4 = (-1) + 1 + (-1) + 1 = 0 \ge 0$ and $a_1 \cdot a_2 \cdot a_3 \cdot a_4 = (-1) \cdot 1 \cdot (-1) \cdot 1 = 1$. Thus, all conditions are already satisfied and no operations are needed.

In the fourth test case, we can assign the values $a_1 := 1, a_2 := 1, a_3 := 1$. Then $a_1 + a_2 + a_3 = 1 + 1 + 1 = 3 \ge 0$ and $a_1 \cdot a_2 \cdot a_3 = 1 \cdot 1 \cdot 1 = 1$. Thus, we performed $3$ operations.

### Sample Input
```
74-1 -1 1 -15-1 -1 -1 1 14-1 1 -1 13-1 -1 -151 1 1 1 11-12-1 -1
```

### Sample Output
```
1
1
0
3
0
1
2
```

---

## Submitted Code

```java
/**
 * author:  Pratham Parikh
 * created: 27.10.2025 22:25:33 IST
**/
 
import java.io.*;
import java.util.*;
 
public class Main {
 
    private static void solve(FastScanner sc) throws Exception {
        int t = sc.nextInt();
        while (t-- > 0) {
            // Your code
            int n = sc.nextInt();
            int[] arr = new int[n];
            int countPositive = 0;
            int countNegative = 0;
            int ops = 0;
            for (int i = 0; i < n; i++) {
                arr[i] = sc.nextInt();
                if (arr[i] == -1) {
                    countNegative++;
                }
            }
 
            countPositive = n - countNegative;
 
            int deficit = countNegative - countPositive;
            if (deficit > 0) {
                ops = (deficit + 1) / 2;
            }
            countNegative -= ops;
            countPositive += ops;
            if (countNegative % 2 != 0) {
                ops += 1;
            }
            System.out.println(ops);
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
- greedy
- math
