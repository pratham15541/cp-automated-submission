
# Reverse XOR (1300)

**Platform:** Codeforces  

**Author:** pratham15541  

**Submitted at:** 11/1/2025, 11:16:56 AM  

**Language:** Java 21  

**Verdict:** OK  

**Time:** 296 ms  

**Memory:** 1300.0 KB  

**Problem URL:** [https://codeforces.com/problemset/problem/2160/C](https://codeforces.com/problemset/problem/2160/C)  

**Submission URL:** [https://codeforces.com/contest/2160/submission/346952228](https://codeforces.com/contest/2160/submission/346952228)  

---

## Problem Statement
Given a positive integer $x$, let $f(x)$ be the positive integer formed by reversing the binary representation of $x$ without leading zeroes. For example, if $x=12=1100_2$, then $f(x)=0011_2=3$. 

You are given an integer $n$. Please determine if there exists a positive integer $x$ such that $x \oplus f(x) = n$^{\text{∗}}$.

$^{\text{∗}}$Here,$\oplus$denotes the bitwise XOR operation. 

ExampleNoteIn the first case, when$x=1$,$f(x)=1$, and$x \oplus f(x)=0$. Thus, the answer is YES.

In the second case, when$x=2$,$f(x)=1$, and$x \oplus f(x)=3$. Thus, the answer is YES.

In the fourth test case, we can show there is no$x$that satisfies$x \oplus f(x)=8$$$, so the answer is NO.

### Sample Input
```
6
0
3
6
8
10
11
```

### Sample Output
```
YES
YES
YES
NO
YES
NO
```

---

## Submitted Code

```java
/**
 * author:  Pratham Parikh
 * created: 01.11.2025 15:57:03 IST
**/
 
import java.io.*;
import java.util.*;
 
public class Main {
 
    // ------------------------ main logic start ------------------------
 
    private static void solve(FastScanner sc) throws Exception {
        int t = sc.nextInt();
        while (t-- > 0) {
            int n = sc.nextInt();
 
            if (n == 0) {
  
                System.out.println("YES");
                continue;
            }
 
    
            Deque<Integer> q = new LinkedList<>();
            int tempN = n;
            while (tempN > 0) {
                q.addLast(tempN % 2); // Add to the back
                tempN /= 2;
            }
 
       
            while (!q.isEmpty() && q.peekFirst() == 0) {
                q.removeFirst();
            }
      
 
 
            boolean isPallindrome = true;
            while (q.size() > 1) {
                int a = q.removeFirst();
                int b = q.removeLast();
                if (a != b) {
                    isPallindrome = false;
                    break;
                }
            }
 
            if (!isPallindrome) {
                System.out.println("NO");
                continue;
            }
 
  
            if (q.size() == 1 && q.peekFirst() == 1) {
                System.out.println("NO");
                continue;
            }
 
            System.out.println("YES");
        }
    }
 
    // ------------------------ main logic end ------------------------
 
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
- bitmasks
