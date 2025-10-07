
# Jagged Swaps (800)

**Platform:** Codeforces  

**Author:** pratham15541  

**Submitted at:** 10/6/2025, 3:08:56 AM  

**Language:** Java 21  

**Verdict:** OK  

**Time:** 405 ms  

**Memory:** 1700.0 KB  

**Problem URL:** [https://codeforces.com/problemset/problem/1896/A](https://codeforces.com/problemset/problem/1896/A)  

**Submission URL:** [https://codeforces.com/contest/1896/submission/342148675](https://codeforces.com/contest/1896/submission/342148675)  

---

## Problem Statement
You are given a permutation$^\dagger$ $a$ of size $n$. You can do the following operation 

 
*  Select an index $i$ from $2$ to $n - 1$ such that $a_{i - 1} &lt; a_i$ and $a_i &gt; a_{i+1}$. Swap $a_i$ and $a_{i+1}$. Determine whether it is possible to sort the permutation after a finite number of operations.

$^\dagger$ A permutation is an array consisting of $n$ distinct integers from $1$ to $n$ in arbitrary order. For example, $[2,3,1,5,4]$ is a permutation, but $[1,2,2]$ is not a permutation ($2$ appears twice in the array) and $[1,3,4]$ is also not a permutation ($n=3$ but there is $4$ in the array).

ExampleNoteIn the first test case, the permutation is already sorted.

In the second test case, we can choose index $i=2$ as $1&lt;3$ and $3&gt;2$ to form $[1, 2, 3, 5, 4]$. Then, we can choose index $i=4$ as $3&lt;5$ and $5&gt;4$ to form $[1, 2, 3, 4, 5]$.

In the third test case, it can be proven that it is impossible to sort the permutation.

---

## Submitted Code
(Your solution code goes here)

---

## Problem Tags
- sortings
