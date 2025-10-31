
# Lasers (800)

**Platform:** Codeforces  

**Author:** pratham15541  

**Submitted at:** 10/30/2025, 5:27:01 AM  

**Language:** Java 21  

**Verdict:** OK  

**Time:** 218 ms  

**Memory:** 0.0 KB  

**Problem URL:** [https://codeforces.com/problemset/problem/2148/B](https://codeforces.com/problemset/problem/2148/B)  

**Submission URL:** [https://codeforces.com/contest/2148/submission/346570258](https://codeforces.com/contest/2148/submission/346570258)  

---

## Problem Statement
There is a 2D-coordinate plane that ranges from $(0,0)$ to $(x, y)$. You are located at $(0,0)$ and want to head to $(x, y)$. 

However, there are $n$ horizontal lasers, with the $i$-th laser continuously spanning $(0, a_i)$ to $(x, a_i)$. Additionally, there are also $m$ vertical lasers, with the $i$-th laser continuously spanning $(b_i, 0)$ to $(b_i, y)$.

You may move in any direction to reach $(x, y)$, but your movement must be a continuous curve that lies inside the plane. Every time you cross a vertical or a horizontal laser, it counts as one crossing. Particularly, if you pass through an intersection point between two lasers, it counts as two crossings.

For example, if $x = y = 2$, $n = m = 1$, $a = [1]$, $b = [1]$, the movement can be as follows:

 ![Image](https://espresso.codeforces.com/44cd14d5698957fd058be07680bad092035229a0.png)   What is the minimum number of crossings necessary to reach $(x, y)$?

Example

### Sample Input
```
2
1 1 2 2
1
1
2 1 100000 100000
42 58
32
```

### Sample Output
```
2
3
```

---

## Submitted Code

```java

```

---

## Problem Tags
- geometry
