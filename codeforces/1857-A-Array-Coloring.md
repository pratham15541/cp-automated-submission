
# Array Coloring (800)

**Platform:** Codeforces  

**Author:** pratham15541  

**Submitted at:** 27/10/2025, 6:38:50 pm  

**Language:** Java 21  

**Verdict:** OK  

**Time:** 249 ms  

**Memory:** 300.0 KB  

**Problem URL:** [https://codeforces.com/problemset/problem/1857/A](https://codeforces.com/problemset/problem/1857/A)  

**Submission URL:** [https://codeforces.com/contest/1857/submission/346020152](https://codeforces.com/contest/1857/submission/346020152)  

---

## Problem Statement
You are given an array consisting of $n$ integers. Your task is to determine whether it is possible to color all its elements in two colors in such a way that the sums of the elements of both colors have the same parity and each color has at least one element colored.

For example, if the array is [$1,2,4,3,2,3,5,4$], we can color it as follows: [$\color{blue}{1},\color{blue}{2},\color{red}{4},\color{blue}{3},\color{red}{2},\color{red}{3},\color{red}{5},\color{red}{4}$], where the sum of the blue elements is $6$ and the sum of the red elements is $18$.

ExampleNoteThe first sample is described in the statement.

In the second sample, there are only two colorings $[\color{blue}{4},\color{red}{7}]$ and $[\color{red}{4},\color{blue}{7}]$ , but in both cases the parity of sums is different.

In the third sample, you can color $[\color{blue}{3},\color{blue}{9},\color{red}{8}]$ and $12$ and $8$ are both even.

### Sample Input
```
781 2 4 3 2 3 5 424 733 9 821 755 4 3 2 144 3 4 5250 48
```

### Sample Output
```
YES
NO
YES
YES
NO
YES
YES
```

---

## Submitted Code

```java
/**
 * author:  Pratham Parikh
 * created: 27.10.2025 18:34:09 IST
**/
 
import java.io.*;
import java.util.*;
 
public class Main {
 
    private static void solve(FastScanner sc) throws Exception {
        int t = sc.nextInt();
        while (t-- > 0) {
            int n = sc.nextInt();
            int sum = 0;
            for (int i = 0; i < n; i++) {
                sum += sc.nextInt();
            }
 
            System.out.println(sum%2==0 ? "YES" : "NO");
 
        }
    }
 
    public static void main(String[] args) {
        long startTime = System.nanoTime();
 
        try {
            FastScanner sc = new FastScanner();
            solve(sc);
        } catch (Exception e) {
            e.printStackTrace();
        }
 
        long endTime = System.nanoTime();
 
        double timeMs = (endTime - startTime) / 1e6;
        System.err.printf("Time measured: %.6f ms%n", timeMs);
 
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
