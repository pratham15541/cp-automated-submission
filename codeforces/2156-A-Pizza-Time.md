
# Pizza Time (Unrated)

**Platform:** Codeforces  

**Author:** pratham15541  

**Submitted at:** 10/26/2025, 6:08:15 AM  

**Language:** Java 21  

**Verdict:** OK  

**Time:** 265 ms  

**Memory:** 500.0 KB  

**Problem URL:** [https://codeforces.com/problemset/problem/2156/A](https://codeforces.com/problemset/problem/2156/A)  

**Submission URL:** [https://codeforces.com/contest/2156/submission/345838788](https://codeforces.com/contest/2156/submission/345838788)  

---

## Problem Statement
Hao and Alex are good friends. After winning a coding competition together, they received a huge pizza as their prize.

Initially, they are given $n$ slices of pizza. Each day, the following process takes place:

 
*  If there are at most $2$ slices remaining, Alex eats all of them.
*  Otherwise, let $m$ be the current number of slices ($m\ge 3$). Hao splits them into three groups of sizes $m_1$, $m_2$, and $m_3$ such that:$m_1 + m_2 + m_3 = m\text{ and } 1 \le m_1\le m_2\le m_3.$

Then:

 
*  Hao eats $m_1$ slices (the smallest group). 
*  Alex eats $m_2$ slices (the middle group). 
*  The remaining $m_3$ slices (the largest group) are carried over to the next day.  Your task is to determine the maximum total number of slices Hao can eat if he always chooses the partition optimally.

ExampleNoteIn the first test case, Hao can eat $3$ slices as follows:

 
*  Split into $m_1 = 2$, $m_2 = 3$, and $m_3 = 3$. Hao eats $2$ slices, Alex eats $3$ slices, and the remaining $3$ slices are carried over to the next day. 
*  Split into $m_1 = 1$, $m_2 = 1$, and $m_3 = 1$. Hao eats $1$ slice, Alex eats $1$ slice, and the remaining $1$ slice is carried over to the next day. 
*  Only $1$ slice remains, so Alex eats it. In the second test case, Hao can eat $1$ slice as follows:

 
*  Split into $m_1 = 1$, $m_2 = 1$, and $m_3 = 2$. Hao eats $1$ slice, Alex eats $1$ slice, and the remaining $2$ slices are carried over to the next day. 
*  Only $2$ slices remain, so Alex eats them all.

### Sample Input
```
3843
```

### Sample Output
```
311
```

---

## Submitted Code
(Your solution code goes here)

---

## Problem Tags
- brute force
- constructive algorithms
- greedy
