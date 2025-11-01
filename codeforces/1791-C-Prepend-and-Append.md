
# Prepend and Append (800)

**Platform:** Codeforces  

**Author:** pratham15541  

**Submitted at:** 10/31/2025, 5:14:45 AM  

**Language:** Java 21  

**Verdict:** OK  

**Time:** 250 ms  

**Memory:** 500.0 KB  

**Problem URL:** [https://codeforces.com/problemset/problem/1791/C](https://codeforces.com/problemset/problem/1791/C)  

**Submission URL:** [https://codeforces.com/contest/1791/submission/346769270](https://codeforces.com/contest/1791/submission/346769270)  

---

## Problem Statement
Timur initially had a binary string$^{\dagger}$ $s$ (possibly of length $0$). He performed the following operation several (possibly zero) times: 

 
*  Add $\texttt{0}$ to one end of the string and $\texttt{1}$ to the other end of the string. For example, starting from the string $\texttt{1011}$, you can obtain either $\color{red}{\texttt{0}}\texttt{1011}\color{red}{\texttt{1}}$ or $\color{red}{\texttt{1}}\texttt{1011}\color{red}{\texttt{0}}$.  You are given Timur's final string. What is the length of the shortest possible string he could have started with?$^{\dagger}$ A binary string is a string (possibly the empty string) whose characters are either $\texttt{0}$ or $\texttt{1}$.

ExampleNoteIn the first test case, the shortest possible string Timur started with is $\texttt{0}$, and he performed the following operation: $\texttt{0} \to \color{red}{\texttt{1}}\texttt{0}\color{red}{\texttt{0}}$.

In the second test case, the shortest possible string Timur started with is $\texttt{11}$, and he performed the following operation: $\texttt{11} \to \color{red}{\texttt{0}}\texttt{11}\color{red}{\texttt{1}}$.

In the third test case, the shortest possible string Timur started with is $\texttt{10101}$, and he didn't perform any operations.

In the fourth test case, the shortest possible string Timur started with is the empty string (which we denote by $\varepsilon$), and he performed the following operations: $\varepsilon \to \color{red}{\texttt{1}}\texttt{}\color{red}{\texttt{0}} \to \color{red}{\texttt{0}}\texttt{10}\color{red}{\texttt{1}} \to \color{red}{\texttt{1}}\texttt{0101}\color{red}{\texttt{0}}$.

In the fifth test case, the shortest possible string Timur started with is $\texttt{101}$, and he performed the following operations: $\texttt{101} \to \color{red}{\texttt{0}}\texttt{101}\color{red}{\texttt{1}} \to \color{red}{\texttt{1}}\texttt{01011}\color{red}{\texttt{0}}$.

### Sample Input
```
9
3
100
4
0111
5
10101
6
101010
7
1010110
1
1
2
10
2
11
10
1011011010
```

### Sample Output
```
1
2
5
0
3
1
0
2
4
```

---

## Submitted Code

```java
/**
 * author:  Pratham Parikh
 * created: 31.10.2025 10:26:01 IST
**/
 
import java.io.*;
import java.util.*;
 
public class Main {
 
    private static void solve(FastScanner sc) throws Exception {
        int t = sc.nextInt();
        while (t-- > 0) {
            int n = sc.nextInt();
            String s = sc.next();
            if (n == 0) {
                System.out.println(0);
                continue;
            }
 
            int l = 0, r = n - 1;
            while (l <= r && s.charAt(l) != s.charAt(r)) {
                l++;
                r--;
            }
            System.out.println(r - l + 1);
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
- two pointers
