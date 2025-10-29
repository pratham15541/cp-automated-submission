
# Mukhammadali and the Smooth Array (Unrated)

**Platform:** Codeforces  

**Author:** pratham15541  

**Submitted at:** 28/10/2025, 9:28:08 pm  

**Language:** Java 21  

**Verdict:** OK  

**Time:** 609 ms  

**Memory:** 700.0 KB  

**Problem URL:** [https://codeforces.com/problemset/problem/2167/G](https://codeforces.com/problemset/problem/2167/G)  

**Submission URL:** [https://codeforces.com/contest/2167/submission/346312141](https://codeforces.com/contest/2167/submission/346312141)  

---

## Problem Statement
Muhammadali has an integer array $a_1,\dots,a_n$. He can change (replace) any subset of positions; changing position $i$ costs $c_i$ and replaces $a_i$ with any integer of his choice. The positions that he does not change must retain their original values.

After all changes, we call an index $i$ ($1 \le i &lt; n$) a drop if the final value at position $i$ is strictly greater than the final value at position $i+1$. Muhammadali wants the final array to contain no drops.

Find the minimum cost of changes required to ensure that there are no drops in the array.

ExampleNoteIn the first and second examples, the array already has no drops, so no changes are needed.

In the third example, one of the optimal arrays is: $[2,3,5,6]$; to achieve this, all elements except the second need to be replaced, so the answer is $c_1 + c_3 + c_4 = 3$.

### Sample Input
```
10
1
10
5
4
1 2 2 3
5 6 7 8
4
4 3 2 1
1 1 1 1
3
3 1 2
100 1 1
5
5 5 5 5 5
10 1 10 1 10
5
1 3 2 2 4
100 1 1 1 100
6
10 9 8 7 6 5
1 100 1 100 1 100
5
100 1 100 100 100
1 100 1 1 1
4
2 1 2 1
5 4 3 2
7
1 5 3 4 2 6 7
10 1 10 1 10 1 10
```

### Sample Output
```
0
0
3
2
0
1
203
1
6
11
```

---

## Submitted Code

```java
/**
 * author:  Pratham Parikh
 * created: 28.10.2025 21:16:31 IST
**/
 
import java.io.*;
import java.util.*;
 
public class Main {
     private static long minCostNoDropsOptimized(int n, int[] a, int[] c) {
        TreeSet<Integer> set = new TreeSet<>();
        for (int val : a) set.add(val);
        int m = set.size();
        int[] vals = new int[m];
        int idx = 0;
        for (int val : set) vals[idx++] = val;
        
        long[] dpPrev = new long[m];
        Arrays.fill(dpPrev, 0);
        
        for (int i = 0; i < n; i++) {
            long[] dpCurr = new long[m];
            long[] prefixMin = new long[m];
            prefixMin[0] = dpPrev[0];
            for (int j = 1; j < m; j++) {
                prefixMin[j] = Math.min(prefixMin[j - 1], dpPrev[j]);
            }
            
            for (int j = 0; j < m; j++) {
                long cost = (vals[j] == a[i]) ? 0 : c[i];
                dpCurr[j] = prefixMin[j] + cost;
            }
            
            dpPrev = dpCurr;
        }
        
        long ans = Long.MAX_VALUE;
        for (long v : dpPrev) ans = Math.min(ans, v);
        return ans;
    }
 
    private static void solve(FastScanner sc) throws Exception {
        int t = sc.nextInt();
        while (t-- > 0) {
            int n = sc.nextInt();
            int[] a = new int[n];
            int[] c = new int[n];
            for(int i=0;i<n;i++){
                a[i] = sc.nextInt();
            }
            for(int i=0;i<n;i++){
                c[i] = sc.nextInt();
            }
            long answer = minCostNoDropsOptimized(n, a, c);
            System.out.println(answer);
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
- data structures
- dp
