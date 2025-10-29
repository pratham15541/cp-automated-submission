
# United We Stand (800)

**Platform:** Codeforces  

**Author:** pratham15541  

**Submitted at:** 10/24/2025, 10:37:03 AM  

**Language:** Java 21  

**Verdict:** OK  

**Time:** 405 ms  

**Memory:** 900.0 KB  

**Problem URL:** [https://codeforces.com/problemset/problem/1859/A](https://codeforces.com/problemset/problem/1859/A)  

**Submission URL:** [https://codeforces.com/contest/1859/submission/345485485](https://codeforces.com/contest/1859/submission/345485485)  

---

## Problem Statement
Given an array $a$ of length $n$, containing integers. And there are two initially empty arrays $b$ and $c$. You need to add each element of array $a$ to exactly one of the arrays $b$ or $c$, in order to satisfy the following conditions:

 
*  Both arrays $b$ and $c$ are non-empty. More formally, let $l_b$ be the length of array $b$, and $l_c$ be the length of array $c$. Then $l_b, l_c \ge 1$. 
*  For any two indices $i$ and $j$ ($1 \le i \le l_b, 1 \le j \le l_c$), $c_j$ is not a divisor of $b_i$. Output the arrays $b$ and $c$ that can be obtained, or output $-1$ if they do not exist.

ExampleNoteIn the first test case, a solution does not exist.

In the second test case, we can obtain $b = [1, 3, 5]$ and $c = [2, 4]$. Then elements $2$ and $4$ do not divide elements $1, 3$ and $5$.

In the fifth test case, we can obtain $b = [4, 8, 4]$ and $c = [12, 12]$.

### Sample Input
```
532 2 251 2 3 4 531 3 571 7 7 2 9 1 454 8 12 12 4
```

### Sample Output
```
-1
3 2
1 3 5 
2 4 
1 2
1 
3 5 
2 5
1 1 
2 4 7 7 9 
3 2
4 8 4 
12 12
```

---

## Submitted Code
```java 21
(Your solution code goes here)
```

---

## Problem Tags
- constructive algorithms
- math
- number theory
