
# Forbidden Integer (800)

**Platform:** Codeforces  

**Author:** pratham15541  

**Submitted at:** 27/10/2025, 7:22:41 pm  

**Language:** Java 21  

**Verdict:** OK  

**Time:** 280 ms  

**Memory:** 2000.0 KB  

**Problem URL:** [https://codeforces.com/problemset/problem/1845/A](https://codeforces.com/problemset/problem/1845/A)  

**Submission URL:** [https://codeforces.com/contest/1845/submission/346027737](https://codeforces.com/contest/1845/submission/346027737)  

---

## Problem Statement
You are given an integer $n$, which you want to obtain. You have an unlimited supply of every integer from $1$ to $k$, except integer $x$ (there are no integer $x$ at all).

You are allowed to take an arbitrary amount of each of these integers (possibly, zero). Can you make the sum of taken integers equal to $n$?

If there are multiple answers, print any of them.

ExampleNoteAnother possible answer for the first testcase is $[3, 3, 3, 1]$. Note that you don't have to minimize the amount of taken integers. There also exist other answers.

In the second testcase, you only have an unlimited supply of integer $2$. There is no way to get sum $5$ using only them.

In the fifth testcase, there are no integers available at all, so you can't get any positive sum.

### Sample Input
```
510 3 25 2 14 2 17 7 36 1 1
```

### Sample Output
```
YES
6
3 1 1 1 1 3
NO
YES
2
2 2
YES
1
7
NO
```

---

## Submitted Code

```java
/**
 * author:  Pratham Parikh
 * created: 27.10.2025 18:54:31 IST
 **/
import java.io.*;
import java.util.*;
 
public class Main {
 
    private static void solve(FastScanner sc) throws Exception {
        int t = sc.nextInt();
        while (t-- > 0) {
            int n = sc.nextInt();
            int k = sc.nextInt();
            int x = sc.nextInt();
 
            List<Integer> arr = new ArrayList<>();
 
            // Case 1: x != 1 -> always possible using only 1's
            if (x != 1) {
                System.out.println("YES");
                System.out.println(n);
                for (int i = 0; i < n; i++) System.out.print("1 ");
                System.out.println();
            } 
            // Case 2: x == 1
            else {
                if (k == 1) {
                    System.out.println("NO");
                } else if (n % 2 == 0) {
                    // use only 2's
                    System.out.println("YES");
                    System.out.println(n / 2);
                    for (int i = 0; i < n / 2; i++) System.out.print("2 ");
                    System.out.println();
                } else if (k >= 3) {
                    // one 3 + rest 2's
                    System.out.println("YES");
                    System.out.println((n - 3) / 2 + 1);
                    System.out.print("3 ");
                    for (int i = 0; i < (n - 3) / 2; i++) System.out.print("2 ");
                    System.out.println();
                } else {
                    System.out.println("NO");
                }
            }
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
        private final byte[] buffer = new byte[1 << 16];
        private int ptr = 0, len = 0;
        FastScanner() { in = System.in; }
 
        private int readByte() throws IOException {
            if (ptr >= len) {
                ptr = 0;
                len = in.read(buffer);
                if (len <= 0) return -1;
            }
            return buffer[ptr++];
        }
 
        int nextInt() throws IOException {
            int c = readByte();
            while (c <= ' ') c = readByte();
            int sign = 1;
            if (c == '-') { sign = -1; c = readByte(); }
            int val = 0;
            while (c >= '0' && c <= '9') {
                val = val * 10 + (c - '0');
                c = readByte();
            }
            return val * sign;
        }
    }
}
```

---

## Problem Tags
- constructive algorithms
- implementation
- math
- number theory
