
# Square? (Unrated)

**Platform:** Codeforces  

**Author:** pratham15541  

**Submitted at:** 28/10/2025, 8:12:21 pm  

**Language:** Java 21  

**Verdict:** OK  

**Time:** 312 ms  

**Memory:** 0.0 KB  

**Problem URL:** [https://codeforces.com/problemset/problem/2167/A](https://codeforces.com/problemset/problem/2167/A)  

**Submission URL:** [https://codeforces.com/contest/2167/submission/346210701](https://codeforces.com/contest/2167/submission/346210701)  

---

## Problem Statement
You are given $4$ sticks of lengths $a$, $b$, $c$, and $d$. You can not break or bend them.

Determine whether it is possible to form a square$^{\text{∗}}$ using the given sticks.

$^{\text{∗}}$A square is defined as a polygon consisting of $4$ vertices, of which all sides have equal length and all inner angles are equal. No two edges of the polygon may intersect each other.

ExampleNoteIn the first test case, we can prove that we can't make a square.

In the second, third, and sixth test cases, we can make a square like this:

 ![Image](https://espresso.codeforces.com/e51fcf1a3ba1663730b9f7ce5a8427c0796be6ca.png)

### Sample Input
```
7
1 2 3 4
1 1 1 1
2 2 2 2
1 2 1 2
1 1 5 5
5 5 5 5
4 10 5 9
```

### Sample Output
```
NO
YES
YES
NO
NO
YES
NO
```

---

## Submitted Code

```java
/**
 * author:  Pratham Parikh
 * created: 28.10.2025 20:10:15 IST
**/
 
import java.io.*;
import java.util.*;
 
public class Main {
 
    private static void solve(FastScanner sc) throws Exception {
        int t = sc.nextInt();
        while (t-- > 0) {
            int a = sc.nextInt();
            int b = sc.nextInt();
            int c = sc.nextInt();
            int d = sc.nextInt();
            System.out.println(a==b&& b==c&&c==d ? "YES":"NO");
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
- implementation
- math
