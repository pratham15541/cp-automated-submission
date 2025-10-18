
# Beautiful Average (Unrated)

**Platform:** Codeforces  

**Author:** pratham15541  

**Submitted at:** 10/17/2025, 4:24:48 PM  

**Language:** Java 21  

**Verdict:** OK  

**Time:** 296 ms  

**Memory:** 600.0 KB  

**Problem URL:** [https://codeforces.com/problemset/problem/2162/A](https://codeforces.com/problemset/problem/2162/A)  

**Submission URL:** [https://codeforces.com/contest/2162/submission/344344835](https://codeforces.com/contest/2162/submission/344344835)  

---

## Problem Statement
You are given an array $a$ of length $n$.

Your task is to find the maximum possible average value of any subarray$^{\text{∗}}$ of the array $a$.

Formally, for any indices $l, r$ such that $1 \le l \le r \le n$, define the average of the subarray $a_l, a_{l+1}, \dots, a_r$ as the sum of elements divided by the number of elements or: $$\texttt{avg}(l,r) = \frac{1}{r-l+1} \sum_{i=l}^{r} a_i$$ Output the maximum value of $\texttt{avg}(l,r)$ over all choices of $l, r$.

$^{\text{∗}}$An array $b$ is a subarray of an array $a$ if $b$ can be obtained from $a$ by deletion of several (possibly, zero or all) elements from the beginning and several (possibly, zero or all) elements from the end. In particular, an array is a subarray of itself. 

Example

---

## Submitted Code
(Your solution code goes here)

---

## Problem Tags
- brute force
- greedy
