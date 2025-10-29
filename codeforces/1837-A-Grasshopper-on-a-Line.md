
# Grasshopper on a Line (800)

**Platform:** Codeforces  

**Author:** pratham15541  

**Submitted at:** 27/10/2025, 10:16:44 pm  

**Language:** Java 21  

**Verdict:** OK  

**Time:** 218 ms  

**Memory:** 700.0 KB  

**Problem URL:** [https://codeforces.com/problemset/problem/1837/A](https://codeforces.com/problemset/problem/1837/A)  

**Submission URL:** [https://codeforces.com/contest/1837/submission/346054835](https://codeforces.com/contest/1837/submission/346054835)  

---

## Problem Statement
You are given two integers $x$ and $k$. Grasshopper starts in a point $0$ on an OX axis. In one move, it can jump some integer distance, that is not divisible by $k$, to the left or to the right.

What's the smallest number of moves it takes the grasshopper to reach point $x$? What are these moves? If there are multiple answers, print any of them.

Example

### Sample Input
```
310 210 33 4
```

### Sample Output
```
2
7 3
1
10
1
3
```

---

## Submitted Code

```java
/**
 * author:  Pratham Parikh
 * created: 27.10.2025 22:11:01 IST
**/
 
import java.io.*;
import java.util.*;
 
public class Main {
 
    private static void solve(FastScanner sc) throws Exception {
        int t = sc.nextInt();
        while (t-- > 0) {
            int x = sc.nextInt();
            int k = sc.nextInt();
            List<Integer> moves = new ArrayList<>();
 
            if (x % k != 0) {
                moves.add(x);
            } else {
                moves.add(x - 1);
                moves.add(1);
            }
 
            System.out.println(moves.size());
 
            for (int i = 0; i < moves.size(); i++) {
                System.out.print(moves.get(i) + (i == moves.size() - 1 ? "\n" : " "));
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
- constructive algorithms
- math
