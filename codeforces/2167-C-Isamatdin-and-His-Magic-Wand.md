
# Isamatdin and His Magic Wand! (Unrated)

**Platform:** Codeforces  

**Author:** pratham15541  

**Submitted at:** 28/10/2025, 8:49:04 pm  

**Language:** Java 21  

**Verdict:** OK  

**Time:** 483 ms  

**Memory:** 500.0 KB  

**Problem URL:** [https://codeforces.com/problemset/problem/2167/C](https://codeforces.com/problemset/problem/2167/C)  

**Submission URL:** [https://codeforces.com/contest/2167/submission/346273713](https://codeforces.com/contest/2167/submission/346273713)  

---

## Problem Statement
Isamatdin has $n$ toys arranged in a row. The $i$-th toy has an integer $a_i$. He wanted to sort them because otherwise, his mother would scold him.

However, Isamatdin never liked arranging toys in order, so his friend JahonaliX gave him a magic wand to help. Unfortunately, JahonaliX made a small mistake while creating the wand.

But Isamatdin couldn't wait any longer and decided to use the broken wand anyway. The wand can only swap two toys if their integers have different parity (one is even, the other is odd). In other words, you can swap toys in positions $(i, j)$ only if $a_i \bmod 2 \neq a_j \bmod 2$, where $\bmod$&nbsp;— is the remainder of integer division.

Now he wants to know the lexicographically smallest$^{\text{∗}}$ arrangement he can achieve using this broken wand.

$^{\text{∗}}$A sequence $p$ is lexicographically smaller than a sequence $q$ if there exists an index $i$ such that $p_j = q_j$ for all $j &lt; i$, and $p_i &lt; q_i$.

ExampleNoteIn the first test case, we can swap positions $(1, 3)$ and then $(2, 3)$.

In the second test case, we can swap positions $(1, 2)$, $(1, 3)$, and then $(2, 3)$.

In the third and fourth test cases, we can't swap any positions because all toy integers have the same parity.

### Sample Input
```
7
4
2 3 1 4
5
3 2 1 3 4
4
3 7 5 1
2
1000000000 2
3
1 3 5
5
2 5 3 1 7
4
2 4 8 6
```

### Sample Output
```
1 2 3 4 
1 2 3 3 4 
3 7 5 1 
1000000000 2 
1 3 5 
1 2 3 5 7 
2 4 8 6
```

---

## Submitted Code

```java
/**
 * author:  Pratham Parikh
 * created: 28.10.2025 20:27:18 IST
**/
 
import java.io.*;
import java.util.*;
 
public class Main {
 
    private static void solve(FastScanner sc) throws Exception {
         int t = sc.nextInt();
        StringBuilder out = new StringBuilder();
        
        while (t-- > 0) {
            int n = sc.nextInt();
            int[] arr = new int[n];
            boolean hasEven = false, hasOdd = false;
 
            for (int i = 0; i < n; i++) {
                arr[i] = sc.nextInt();
                if (arr[i] % 2 == 0) hasEven = true;
                else hasOdd = true;
            }
 
            // Check if already sorted
            boolean sorted = true;
            for (int i = 1; i < n; i++) {
                if (arr[i - 1] > arr[i]) {
                    sorted = false;
                    break;
                }
            }
 
            if (sorted || (hasEven && hasOdd)) {
                Arrays.sort(arr);
            }
 
            for (int i = 0; i < n; i++) {
                out.append(arr[i]).append(" ");
            }
            out.append("\n");
        }
 
        System.out.println(out.toString());
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
- greedy
- implementation
- sortings
