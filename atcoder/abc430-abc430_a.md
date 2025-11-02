# A - Candy Cookie Law
			Editorial (AC)

**Platform:** AtCoder  

**Author:** pratham15541  

**Submitted at:** 2025-11-01 18:07:12

**Language:** Java24  

**Runtime:** 41ms

**Memory:** N/A  

**Problem URL:** [https://atcoder.jp/contests/abc430/tasks/abc430_a](https://atcoder.jp/contests/abc430/tasks/abc430_a)  

**Submission URL:** [https://atcoder.jp/contests/abc430/submissions/70610063](https://atcoder.jp/contests/abc430/submissions/70610063)  

---

## Problem Statement
<p>Score : <var>100</var> points</p>

<section>
<h3>Problem Statement</h3><p>In AtCoder Country where Takahashi lives, there is a strange law that "a person who possesses <var>A</var> or more candies must possess <var>B</var> or more cookies."</p>
<p>Takahashi possesses <var>C</var> candies and <var>D</var> cookies. Determine whether Takahashi is violating this law.</p>
</section>

<section>
<h3>Constraints</h3><ul>
<li><var>1\leq A,B,C,D \leq 100</var></li>
<li>All input values are integers.</li>
</ul>
</section>
<hr>
<section>
<h3>Input</h3><p>The input is given from Standard Input in the following format:</p>
<pre><var>A</var> <var>B</var> <var>C</var> <var>D</var>
</pre>
</section>

<section>
<h3>Output</h3><p>Print <code>Yes</code> if Takahashi is violating the law, and <code>No</code> otherwise.</p>
</section>
<hr>

<section>
<h3>Sample Input 1</h3><pre>10 20 30 40
</pre>
</section>

<section>
<h3>Sample Output 1</h3><pre>No
</pre>
<p>In AtCoder Country, there is a law that "a person who possesses <var>10</var> or more candies must possess <var>20</var> or more cookies."</p>
<p>Takahashi possesses <var>30</var> candies and <var>40</var> cookies, so he is not violating this law.</p>
</section>
<hr>

<section>
<h3>Sample Input 2</h3><pre>10 20 30 4
</pre>
</section>

<section>
<h3>Sample Output 2</h3><pre>Yes
</pre>
</section>
<hr>

<section>
<h3>Sample Input 3</h3><pre>100 100 1 1
</pre>
</section>

<section>
<h3>Sample Output 3</h3><pre>No
</pre></section>

---

## Submitted Code
```java
/**
 * author:  Pratham Parikh
 * created: 01.11.2025 17:51:34 IST
**/

import java.io.*;
import java.util.*;

public class Main {

    // ------------------------ main logic start ------------------------

    private static void solve(FastScanner sc) throws Exception {
        int A = sc.nextInt();
        int B = sc.nextInt();
        int C = sc.nextInt();
        int D = sc.nextInt();

        

        if (C >= A && D < B) {
            System.out.println("Yes");
        } else {
            System.out.println("No");
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