# C - Truck Driver
			Editorial (AC)

**Platform:** AtCoder  

**Author:** pratham15541  

**Submitted at:** 2025-11-01 18:53:31

**Language:** Java24  

**Runtime:** 94ms

**Memory:** N/A  

**Problem URL:** [https://atcoder.jp/contests/abc430/tasks/abc430_c](https://atcoder.jp/contests/abc430/tasks/abc430_c)  

**Submission URL:** [https://atcoder.jp/contests/abc430/submissions/70622915](https://atcoder.jp/contests/abc430/submissions/70622915)  

---

## Problem Statement
<p>Score : <var>300</var> points</p>

<section>
<h3>Problem Statement</h3><blockquote>
<p>In AtCoder Country, there is a rule that "a truck driver must take a break of at least <var>B</var> minutes when driving for <var>A</var> minutes or more."</p>
</blockquote>
<p>You are given a string <var>S</var> of length <var>N</var> consisting of <code>a</code> and <code>b</code>, and positive integers <var>A</var> and <var>B</var>. Find the number of integer pairs <var>(l,r)</var> that satisfy all of the following conditions.</p>
<ul>
<li><var>1\leq l \leq r \leq N</var></li>
<li>The number of <code>a</code> in the substring from the <var>l</var>-th character through the <var>r</var>-th character of <var>S</var> is greater than or equal to <var>A</var>.</li>
<li>The number of <code>b</code> in the substring from the <var>l</var>-th character through the <var>r</var>-th character of <var>S</var> is less than <var>B</var>.</li>
</ul>
</section>

<section>
<h3>Constraints</h3><ul>
<li><var>1\leq N \leq 3\times 10^5</var></li>
<li><var>1 \leq A,B \leq N</var></li>
<li><var>S</var> is a string of length <var>N</var> consisting of <code>a</code> and <code>b</code>.</li>
<li>All input numbers are integers.</li>
</ul>
</section>
<hr>
<section>
<h3>Input</h3><p>The input is given from Standard Input in the following format:</p>
<pre><var>N</var> <var>A</var> <var>B</var>
<var>S</var>
</pre>
</section>

<section>
<h3>Output</h3><p>Print the answer.</p>
</section>
<hr>

<section>
<h3>Sample Input 1</h3><pre>11 4 2
abbaaabaaba
</pre>
</section>

<section>
<h3>Sample Output 1</h3><pre>3
</pre>
<p>The pairs <var>(l,r)</var> that satisfy the conditions are <var>(4,8),(4,9),(5,9)</var>, which is three pairs.</p>
</section>
<hr>

<section>
<h3>Sample Input 2</h3><pre>13 1 2
bbbbbbbbbbbbb
</pre>
</section>

<section>
<h3>Sample Output 2</h3><pre>0
</pre>
<p>There are no pairs <var>(l,r)</var> that satisfy the conditions.</p></section>

---

## Submitted Code
```java
/**
 * author:  Pratham Parikh
 * created: 01.11.2025 18:23:26 IST
**/

import java.io.*;
import java.util.*;

public class Main {

    // ------------------------ main logic start ------------------------

    private static void solve(FastScanner sc) throws Exception {

        int N = (int) sc.nextLong();
        long A = sc.nextLong();
        long B = sc.nextLong();
        String s = sc.next();

        long totalCount = 0;

        int L_A = 0;
        long current_a_count = 0;

        int L_B = 0;
        long current_b_count = 0;

        for (int j = 0; j < N; j++) {
            if (s.charAt(j) == 'a') {
                current_a_count++;
            } else {
                current_b_count++;
            }

            while (L_A <= j && current_a_count >= A) {
                if (s.charAt(L_A) == 'a') {
                    current_a_count--;
                }
                L_A++;
            }

            int max_start_A = L_A - 1;

            while (L_B <= j && current_b_count >= B) {
                if (s.charAt(L_B) == 'b') {
                    current_b_count--;
                }
                L_B++;
            }

            int min_start_B = L_B;

            int valid_starts = max_start_A - min_start_B + 1;

            if (valid_starts > 0) {
                totalCount += valid_starts;
            }
        }

        System.out.println(totalCount);
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