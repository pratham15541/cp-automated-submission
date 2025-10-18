
# Beautiful String (Unrated)

**Platform:** Codeforces  

**Author:** pratham15541  

**Submitted at:** 10/17/2025, 4:26:49 PM  

**Language:** Java 21  

**Verdict:** OK  

**Time:** 296 ms  

**Memory:** 600.0 KB  

**Problem URL:** [https://codeforces.com/problemset/problem/2162/B](https://codeforces.com/problemset/problem/2162/B)  

**Submission URL:** [https://codeforces.com/contest/2162/submission/344346840](https://codeforces.com/contest/2162/submission/344346840)  

---

## Problem Statement
You are given a binary$^{\text{∗}}$ string $s$ of length $n$.

Your task is to find any subsequence$^{\text{†}}$ $p$ of $s$ such that:

 
*  The subsequence $p$ is non-decreasing. That is, each character in $p$ is not greater than the next one. 
*  Let $x$ denote the string obtained by removing all characters of $p$ from $s$, while preserving the order of the remaining characters. Then $x$ must be a palindrome$^{\text{‡}}$. You only need to output any valid subsequence $p$ that satisfies both conditions. If no such subsequence exists, output $-1$.

Note that an empty string is both non-decreasing and a palindrome.

$^{\text{∗}}$A binary string is a string consisting of characters '0' and '1'.

$^{\text{†}}$A subsequence of a string $s = s_1s_2\ldots s_n$ is a sequence $p = s_{i_1}s_{i_2}\ldots s_{i_k}$ such that $1 \leq i_1 &lt; i_2 &lt; \ldots &lt; i_k \leq n$. The characters are selected in order, but not necessarily contiguously. Note that an empty string is a subsequence of any string. 

$^{\text{‡}}$A string $t = t_1t_2\ldots t_m$ is a palindrome if $t_i = t_{m - i + 1}$ for all $1 \leq i \leq m$. In other words, the string reads the same forward and backward. 

ExampleNoteIn the first test case, we remove an empty string, resulting in $x = \texttt{010}$, which is a palindrome.

In the second test case, we remove $p = \texttt{01}$ (indices $2$, $3$), resulting in $x = \texttt{0}$, which is a palindrome.

In the third test case, we remove $p = \texttt{00111}$ (indices $1$ to $5$), resulting in an empty string, which is trivially a palindrome.

In the fourth test case, we remove $p = \texttt{01}$ (indices $3$, $4$), resulting in $x = \texttt{110011}$, which is a palindrome.

In the fifth test case, we remove $p = \texttt{01}$ (indices $5$, $6$), resulting in $x = \texttt{1001}$, which is a palindrome.

---

## Submitted Code
(Your solution code goes here)

---

## Problem Tags
- constructive algorithms
