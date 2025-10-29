
# Don't Try to Count (800)

**Platform:** Codeforces  

**Author:** pratham15541  

**Submitted at:** 10/19/2025, 6:13:22 AM  

**Language:** Java 21  

**Verdict:** OK  

**Time:** 343 ms  

**Memory:** 1000.0 KB  

**Problem URL:** [https://codeforces.com/problemset/problem/1881/A](https://codeforces.com/problemset/problem/1881/A)  

**Submission URL:** [https://codeforces.com/contest/1881/submission/344592231](https://codeforces.com/contest/1881/submission/344592231)  

---

## Problem Statement
Given a string $x$ of length $n$ and a string $s$ of length $m$ ($n \cdot m \le 25$), consisting of lowercase Latin letters, you can apply any number of operations to the string $x$.

In one operation, you append the current value of $x$ to the end of the string $x$. Note that the value of $x$ will change after this.

For example, if $x =$"aba", then after applying operations, $x$ will change as follows: "aba" $\rightarrow$ "abaaba" $\rightarrow$ "abaabaabaaba".

After what minimum number of operations $s$ will appear in $x$ as a substring? A substring of a string is defined as a contiguous segment of it.

ExampleNoteIn the first test case of the example, after $2$ operations, the string will become "aaaa", and after $3$ operations, it will become "aaaaaaaa", so the answer is $3$.

In the second test case of the example, after applying $1$ operation, the string will become "$\text{e}\color{red}{\text{force}}\text{forc}$", where the substring is highlighted in red.

In the fourth test case of the example, it can be shown that it is impossible to obtain the desired string as a substring.

---

## Submitted Code
(Your solution code goes here)

---

## Problem Tags
- brute force
- strings
