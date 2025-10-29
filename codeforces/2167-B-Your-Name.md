
# Your Name (Unrated)

**Platform:** Codeforces  

**Author:** pratham15541  

**Submitted at:** 28/10/2025, 8:25:20 pm  

**Language:** Java 21  

**Verdict:** OK  

**Time:** 234 ms  

**Memory:** 400.0 KB  

**Problem URL:** [https://codeforces.com/problemset/problem/2167/B](https://codeforces.com/problemset/problem/2167/B)  

**Submission URL:** [https://codeforces.com/contest/2167/submission/346241246](https://codeforces.com/contest/2167/submission/346241246)  

---

## Problem Statement
khba is writing his girlfriend's name. He has $n$ cubes, each with one lowercase Latin letter written on it. They are arranged in a row, forming a string $s$. His girlfriend's name is also a string $t$, consisting of $n$ lowercase Latin letters.

To prove his love, he must check whether it is possible to rearrange the letters of string $s$ so that it becomes her name $t$.

ExampleNoteIn the first example, the initial string is "humitsa", and the following operations can be performed: 

 
*  swap the first and third characters, resulting in "muhitsa" 
*  swap the second and fourth characters, resulting in "mihutsa" 
*  swap the third and fifth characters, resulting in "mithusa" 
*  swap the fourth and sixth characters, resulting in "mitsuha" In the second example, the initial string is "orhi", and the following operations can be performed: 

 
*  swap the second and third characters, resulting in "ohri" 
*  swap the first and second characters, resulting in "hori"

### Sample Input
```
5
7
humitsa mitsuha
4
orhi hori
6
aakima makima
6
nezuqo nezuko
6
misaka mikasa
```

### Sample Output
```
YES
YES
NO
NO
YES
```

---

## Submitted Code

```java
/**
 * author:  Pratham Parikh
 * created: 28.10.2025 20:12:55 IST
**/
 
import java.io.*;
import java.util.*;
 
public class Main {
 
    private static void solve(FastScanner sc) throws Exception {
        int q = sc.nextInt();
        while (q-- > 0) {
            int n = sc.nextInt();
            String s= sc.next();
            String t = sc.next();
            
            if(haveSameCharacter(s, t)){
                System.out.println("YES");
            }else{
                System.out.println("NO");
            }
        }
    }
 
     static boolean haveSameCharacter(String s1, String s2){
        if(s1.length() != s2.length()) return false;
        int[] freq = new int[256];
        for(char c: s1.toCharArray()){
            freq[c]++;
        }
        for(char c:s2.toCharArray()){
            freq[c]--;
        }
        for(int f: freq){
            if(f!=0){
                return false;
            }
        }
        return true;
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
- sortings
- strings
