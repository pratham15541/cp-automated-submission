
# Make it Beautiful (800)

**Platform:** Codeforces  

**Author:** pratham15541  

**Submitted at:** 11/1/2025, 11:55:11 AM  

**Language:** Java 21  

**Verdict:** OK  

**Time:** 406 ms  

**Memory:** 1100.0 KB  

**Problem URL:** [https://codeforces.com/problemset/problem/1783/A](https://codeforces.com/problemset/problem/1783/A)  

**Submission URL:** [https://codeforces.com/contest/1783/submission/346958147](https://codeforces.com/contest/1783/submission/346958147)  

---

## Problem Statement
An array $a$ is called ugly if it contains at least one element which is equal to the sum of all elements before it. If the array is not ugly, it is beautiful.

For example:

 
*  the array $[6, 3, 9, 6]$ is ugly: the element $9$ is equal to $6 + 3$; 
*  the array $[5, 5, 7]$ is ugly: the element $5$ (the second one) is equal to $5$; 
*  the array $[8, 4, 10, 14]$ is beautiful: $8 \ne 0$, $4 \ne 8$, $10 \ne 8 + 4$, $14 \ne 8 + 4 + 10$, so there is no element which is equal to the sum of all elements before it. You are given an array $a$ such that $1 \le a_1 \le a_2 \le \dots \le a_n \le 100$. You have to reorder the elements of $a$ in such a way that the resulting array is beautiful. Note that you are not allowed to insert new elements or erase existing ones, you can only change the order of elements of $a$. You are allowed to keep the array $a$ unchanged, if it is beautiful.

Example

### Sample Input
```
4
4
3 3 6 6
2
10 10
5
1 2 3 4 5
3
1 4 4
```

### Sample Output
```
YES
3 6 3 6
NO
YES
2 4 1 5 3
YES
1 4 4
```

---

## Submitted Code

```java
/**
 * author:  Pratham Parikh
 * created: 01.11.2025 16:58:36 IST
**/
 
import java.io.*;
import java.util.*;
 
public class Main {
 
    // ------------------------ main logic start ------------------------
 
    private static int sumArray(int[] arr, int n) {
        int sum = 0;
        for (int i = 0; i < n; i++) {
            sum += arr[i];
        }
        return sum;
    }
 
    private static void solve(FastScanner sc) throws Exception {
        int t = sc.nextInt();
        while (t-- > 0) {
            int n = sc.nextInt();
            int[] arr = sc.readIntArray(n);
            Arrays.sort(arr);
            int max = arr[n - 1];
            int min = arr[0];
            if (min == max) {
                System.out.println("NO");
                continue;
            }
 
            System.out.println("YES");
            System.out.print(max + " ");
            for (int i = 0; i < n - 1; i++)
                System.out.print(arr[i] + " ");
            System.out.println();
 
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
- constructive algorithms
- math
- sortings
