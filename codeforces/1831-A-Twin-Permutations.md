
# Twin Permutations (800)

**Platform:** Codeforces  

**Author:** pratham15541  

**Submitted at:** 10/29/2025, 4:20:29 PM  

**Language:** Java 21  

**Verdict:** OK  

**Time:** 562 ms  

**Memory:** 1800.0 KB  

**Problem URL:** [https://codeforces.com/problemset/problem/1831/A](https://codeforces.com/problemset/problem/1831/A)  

**Submission URL:** [https://codeforces.com/contest/1831/submission/346497258](https://codeforces.com/contest/1831/submission/346497258)  

---

## Problem Statement
You are given a permutation$^\dagger$ $a$ of length $n$.

Find any permutation $b$ of length $n$ such that $a_1+b_1 \le a_2+b_2 \le a_3+b_3 \le \ldots \le a_n+b_n$.

It can be proven that a permutation $b$ that satisfies the condition above always exists.

$^\dagger$ A permutation of length $n$ is an array consisting of $n$ distinct integers from $1$ to $n$ in arbitrary order. For example, $[2,3,1,5,4]$ is a permutation, but $[1,2,2]$ is not a permutation ($2$ appears twice in the array), and $[1,3,4]$ is also not a permutation ($n=3$ but there is $4$ in the array).

ExampleNoteIn the first test case $a=[1, 2, 4, 5, 3]$. Then the permutation $b=[1, 2, 4, 3, 5]$ satisfies the condition because $1 + 1 \le 2 + 2 \le 4 + 4 \le 5 + 3 \le 3 + 5$.

### Sample Input
```
5
5
1 2 4 5 3
2
1 2
1
1
3
3 2 1
4
1 4 3 2
```

### Sample Output
```
1 2 4 3 5
2 1
1
1 2 3
1 2 3 4
```

---

## Submitted Code

```java

```

---

## Problem Tags
- constructive algorithms
