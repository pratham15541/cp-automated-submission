
# One and Two (800)

**Platform:** Codeforces  

**Author:** pratham15541  

**Submitted at:** 10/31/2025, 9:50:51 AM  

**Language:** Java 21  

**Verdict:** OK  

**Time:** 249 ms  

**Memory:** 300.0 KB  

**Problem URL:** [https://codeforces.com/problemset/problem/1788/A](https://codeforces.com/problemset/problem/1788/A)  

**Submission URL:** [https://codeforces.com/contest/1788/submission/346799573](https://codeforces.com/contest/1788/submission/346799573)  

---

## Problem Statement
You are given a sequence $a_1, a_2, \ldots, a_n$. Each element of $a$ is $1$ or $2$.

Find out if an integer $k$ exists so that the following conditions are met. 

 
*  $1 \leq k \leq n-1$, and 
*  $a_1 \cdot a_2 \cdot \ldots \cdot a_k = a_{k+1} \cdot a_{k+2} \cdot \ldots \cdot a_n$. If there exist multiple $k$ that satisfy the given condition, print the smallest.

ExampleNoteFor the first test case, $k=2$ satisfies the condition since $a_1 \cdot a_2 = a_3 \cdot a_4 \cdot a_5 \cdot a_6 = 4$. $k=3$ also satisfies the given condition, but the smallest should be printed.

For the second test case, there is no $k$ that satisfies $a_1 \cdot a_2 \cdot \ldots \cdot a_k = a_{k+1} \cdot a_{k+2} \cdot \ldots \cdot a_n$

For the third test case, $k=1$, $2$, and $3$ satisfy the given condition, so the answer is $1$.

### Sample Input
```
3
6
2 2 1 2 1 2
3
1 2 1
4
1 1 1 1
```

### Sample Output
```
2
-1
1
```

---

## Submitted Code

```java
/**
 * author:  Pratham Parikh
 * created: 31.10.2025 15:07:47 IST
**/
 
import java.io.*;
import java.util.*;
 
public class Main {
 
    // --------------------------------- main logic start
    // ---------------------------------
 
    private static void solve(FastScanner sc) throws Exception {
        int t = sc.nextInt();
        while (t-- > 0) {
            // Your code
            int n = sc.nextInt();
            int[] arr = sc.readIntArray(n);
            int count2 = 0;
            for (int i = 0; i < n; i++) {
                if (arr[i] == 2) {
                    count2++;
                }
            }
 
            if (count2 == 0) {
                System.out.println(1);
                continue;
            }
 
            if (count2 % 2 != 0) {
                System.out.println(-1);
                continue;
            }
            int minCount2 = count2 / 2;
            int count = 0;
            for (int k = 0; k < n; k++) {
                if (count == minCount2) {
                    System.out.println(k);
                    break;
                }
                if (arr[k] == 2) {
                    count++;
                }
            }
 
        }
    }
 
    // --------------------------------- main logic end
    // ------------------------------------
 
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
 
        int[] readIntArray(int n) throws IOException {
            int[] arr = new int[n];
            for (int i = 0; i < n; i++) {
                arr[i] = nextInt();
            }
            return arr;
        }
 
        long[] readLongArray(int n) throws IOException {
            long[] arr = new long[n];
            for (int i = 0; i < n; i++) {
                arr[i] = nextLong();
            }
            return arr;
        }
 
        String[] readStringArray(int n) throws IOException {
            String[] arr = new String[n];
            for (int i = 0; i < n; i++) {
                arr[i] = next();
            }
            return arr;
        }
 
        double[] readDoubleArray(int n) throws IOException {
            double[] arr = new double[n];
            for (int i = 0; i < n; i++) {
                arr[i] = nextDouble();
            }
            return arr;
        }
    }
}
```

---

## Problem Tags
- brute force
- implementation
- math
