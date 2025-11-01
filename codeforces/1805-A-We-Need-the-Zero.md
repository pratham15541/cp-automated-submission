
# We Need the Zero (800)

**Platform:** Codeforces  

**Author:** pratham15541  

**Submitted at:** 10/31/2025, 4:54:28 AM  

**Language:** Java 21  

**Verdict:** OK  

**Time:** 296 ms  

**Memory:** 1600.0 KB  

**Problem URL:** [https://codeforces.com/problemset/problem/1805/A](https://codeforces.com/problemset/problem/1805/A)  

**Submission URL:** [https://codeforces.com/contest/1805/submission/346767588](https://codeforces.com/contest/1805/submission/346767588)  

---

## Problem Statement
There is an array $a$ consisting of non-negative integers. You can choose an integer $x$ and denote $b_i=a_i \oplus x$ for all $1 \le i \le n$, where $\oplus$ denotes the bitwise XOR operation. Is it possible to choose such a number $x$ that the value of the expression $b_1 \oplus b_2 \oplus \ldots \oplus b_n$ equals $0$?

It can be shown that if a valid number $x$ exists, then there also exists $x$ such that ($0 \le x &lt; 2^8$).

ExampleNoteIn the first test case, after applying the operation with the number $6$ the array $b$ becomes $[7, 4, 3]$, $7 \oplus 4 \oplus 3 = 0$.

There are other answers in the third test case, such as the number $0$.

### Sample Input
```
5
3
1 2 5
3
1 2 3
4
0 1 2 3
4
1 2 2 3
1
1
```

### Sample Output
```
6
0
3
-1
1
```

---

## Submitted Code

```java

```

---

## Problem Tags
- bitmasks
- brute force
