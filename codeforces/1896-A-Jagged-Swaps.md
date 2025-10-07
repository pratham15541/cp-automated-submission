
# Jagged Swaps (800)

**Platform:** Codeforces  
**Author:** pratham15541  
**Submitted at:** 6/10/2025, 8:38:56 am  
**Language:** Java 21  
**Verdict:** OK  
**Time:** 405 ms  
**Memory:** 1700.0 KB  
**Problem URL:** [https://codeforces.com/problemset/problem/1896/A](https://codeforces.com/problemset/problem/1896/A)  
**Submission URL:** [https://codeforces.com/contest/1896/submission/342148675](https://codeforces.com/contest/1896/submission/342148675)  

---

## Problem Statement
### A. Jagged Swaps

You are given a permutation$$$^\dagger$$$ $$$a$$$ of size $$$n$$$. You can do the following operation Select an index $$$i$$$ from $$$2$$$ to $$$n - 1$$$ such that $$$a_{i - 1} &lt; a_i$$$ and $$$a_i &gt; a_{i+1}$$$. Swap $$$a_i$$$ and $$$a_{i+1}$$$. Determine whether it is possible to sort the permutation after a finite number of operations.$$$^\dagger$$$ A permutation is an array consisting of $$$n$$$ distinct integers from $$$1$$$ to $$$n$$$ in arbitrary order. For example, $$$[2,3,1,5,4]$$$ is a permutation, but $$$[1,2,2]$$$ is not a permutation ($$$2$$$ appears twice in the array) and $$$[1,3,4]$$$ is also not a permutation ($$$n=3$$$ but there is $$$4$$$ in the array).

#### Input
InputEach test contains multiple test cases. The first line contains the number of test cases $$$t$$$ ($$$1 \le t \le 5000$$$). Description of the test cases follows.The first line of each test case contains a single integer $$$n$$$ ($$$3 \le n \le 10$$$) — the size of the permutation.The second line of each test case contains $$$n$$$ integers $$$a_1, a_2, \ldots, a_n$$$ ($$$1 \le a_i \le n$$$) — the elements of permutation $$$a$$$.

#### Output
OutputFor each test case, print "YES" if it is possible to sort the permutation, and "NO" otherwise.You may print each letter in any case (for example, "YES", "Yes", "yes", "yEs" will all be recognized as positive answer).

#### Samples
**Input:**
```
631 2 351 3 2 5 455 4 3 2 133 1 242 3 1 455 1 2 3 4
```
**Output:**
```
YES
YES
NO
NO
NO
NO
```

---

## Submitted Code
(Your solution code goes here)

---

## Problem Tags
- sortings
