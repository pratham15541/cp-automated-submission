
# Equal Occurrences (800)

**Platform:** Codeforces  

**Author:** pratham15541  

**Submitted at:** 10/8/2025, 6:18:24 AM  

**Language:** Java 21  

**Verdict:** OK  

**Time:** 218 ms  

**Memory:** 300.0 KB  

**Problem URL:** [https://codeforces.com/problemset/problem/2146/A](https://codeforces.com/problemset/problem/2146/A)  

**Submission URL:** [https://codeforces.com/contest/2146/submission/342542162](https://codeforces.com/contest/2146/submission/342542162)  

---

## Problem Statement
We call an array balanced if and only if the numbers of occurrences of any of its elements are the same. For example, $[1,1,3,3,6,6]$ and $[2,2,2,2]$ are balanced, but $[1,2,3,3]$ is not balanced (the numbers of occurrences of elements $1$ and $3$ are different). Note that an empty array is always balanced.

You are given a non-decreasing array $a$ consisting of $n$ integers. Find the length of its longest balanced subsequence$^{\text{∗}}$.

$^{\text{∗}}$A sequence $b$ is a subsequence of a sequence $a$ if $b$ can be obtained from $a$ by the deletion of several (possibly, zero or all) element from arbitrary positions. 

ExampleNoteIn the first test case, the whole array $a = [1, 1, 4, 4, 4]$ is not balanced because the number of occurrences of element $1$ is $2$, while the number of occurrences of element $4$ is $3$, which are not equal. The subsequence $[1, 1, 4, 4]$ is balanced because the numbers of occurrences of elements $1$ and $4$ are both $2$. Thus, the length of the longest balanced subsequence of $a$ is $4$.

In the second test case, the whole array $a = [1, 2]$ is already balanced, so the length of the longest balanced subsequence of $a$ is $2$.

In the third test case, the longest balanced subsequence of $a$ is $[1,1,1,2,2,2,3,3,3]$.

In the fourth test case, the whole array $a = [3, 3, 3, 3, 3]$ is already balanced, so the length of the longest balanced subsequence of $a$ is $5$.

---

## Submitted Code
(Your solution code goes here)

---

## Problem Tags
- brute force
- greedy
- implementation
