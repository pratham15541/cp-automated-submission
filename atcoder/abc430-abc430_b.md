# B - Count Subgrid
			Editorial (AC)

**Platform:** AtCoder  

**Author:** pratham15541  

**Submitted at:** 2025-11-01 18:18:31

**Language:** Java24  

**Runtime:** 40ms

**Memory:** N/A  

**Problem URL:** [https://atcoder.jp/contests/abc430/tasks/abc430_b](https://atcoder.jp/contests/abc430/tasks/abc430_b)  

**Submission URL:** [https://atcoder.jp/contests/abc430/submissions/70613644](https://atcoder.jp/contests/abc430/submissions/70613644)  

---

## Problem Statement
<p>Score : <var>250</var> points</p>

<section>
<h3>Problem Statement</h3><p>There is a grid with <var>N</var> rows and <var>N</var> columns. The cell at the <var>i</var>-th row from the top and <var>j</var>-th column from the left is painted black if <var>S_{i,j}</var> is <code>#</code>, and white if it is <code>.</code>.</p>
<p>How many distinct patterns of painted cells can be obtained by extracting a region of <var>M</var> rows and <var>M</var> columns from this grid?</p>
</section>

<section>
<h3>Constraints</h3><ul>
<li><var>1\leq M \leq N \leq 10</var></li>
<li><var>N</var> and <var>M</var> are integers.</li>
<li><var>S_{i,j}</var> is <code>.</code> or <code>#</code>.</li>
</ul>
</section>
<hr>
<section>
<h3>Input</h3><p>The input is given from Standard Input in the following format:</p>
<pre><var>N</var> <var>M</var>
<var>S_{1,1}\ldots S_{1,N}</var>
<var>\vdots</var>
<var>S_{N,1}\ldots S_{N,N}</var>
</pre>
</section>

<section>
<h3>Output</h3><p>Print the answer.</p>
</section>
<hr>

<section>
<h3>Sample Input 1</h3><pre>3 2
...
###
#.#
</pre>
</section>

<section>
<h3>Sample Output 1</h3><pre>3
</pre>
<p>The state of the given grid is as shown in the left figure below.<br>
There are four ways to extract a region of two rows and two columns from this grid as shown in the right figure below, and there are three distinct patterns of painted cells.</p>
<p><img alt="Figure" src="https://img.atcoder.jp/abc430/f9240b594bb2c8463ffca0c0f7ec1b40.png"></p>
</section>
<hr>

<section>
<h3>Sample Input 2</h3><pre>10 3
..#.......
.###......
.#.#......
#####.....
#...#.....
......####
......#..#
......#...
......#..#
......####
</pre>
</section>

<section>
<h3>Sample Output 2</h3><pre>36
</pre></section>

---

## Submitted Code
```java
/**
 * author:  Pratham Parikh
 * created: 01.11.2025 18:16:57 IST
**/

import java.io.*;
import java.util.*;

public class Main {

    // ------------------------ main logic start ------------------------

    private static void solve(FastScanner sc) throws Exception {
        int N = sc.nextInt(), M = sc.nextInt();
        String[] grid = new String[N];
        for (int i = 0; i < N; i++)
            grid[i] = sc.next();

        HashSet<String> set = new HashSet<>();
        for (int r = 0; r <= N - M; r++) {
            for (int c = 0; c <= N - M; c++) {
                StringBuilder sb = new StringBuilder();
                for (int i = 0; i < M; i++) {
                    for (int j = 0; j < M; j++) {
                        sb.append(grid[r + i].charAt(c + j));
                    }
                }
                set.add(sb.toString());
            }
        }
        System.out.println(set.size());
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