
# Loyalty (Unrated)

**Platform:** Codeforces  

**Author:** pratham15541  

**Submitted at:** 10/30/2025, 6:36:18 PM  

**Language:** Java 21  

**Verdict:** OK  

**Time:** 328 ms  

**Memory:** 1000.0 KB  

**Problem URL:** [https://codeforces.com/problemset/problem/2161/C](https://codeforces.com/problemset/problem/2161/C)  

**Submission URL:** [https://codeforces.com/contest/2161/submission/346719444](https://codeforces.com/contest/2161/submission/346719444)  

---

## Problem Statement
No Loyalty No Royalty (c) You are a customer in a store and want to buy $n$ items. Each item $i$ has a price $a_i$ such that $1 \leq a_i \leq X$, where $X$ is a loyalty factor.

Your loyalty level in the store is defined as $\lfloor {S \over X} \rfloor$, where $S$ is the total cost of items purchased so far. Initially, $S = 0$.

If you buy an item with price $p$ and your loyalty level increases as a result of this purchase, you earn $p$ bonus points.

Your task is to find the maximum number of bonus points you can earn by choosing an optimal order of purchase for the items.

ExampleNoteIn the first test case:

*  After buying the first item $S = 1$, loyalty level is 0;
*  After buying the second item $S = 3$, this increases loyalty level to $1$ and earns $2$ bonus points;
*  After buying the third item $S = 5$, this increases loyalty level to $2$ and earns $2$ bonus points;
*  After buying the fourth item $S = 7$, this increases loyalty level to $3$ and earns $2$ bonus points;
*  After buying the fifth item $S = 9$, this increases loyalty level to $4$ and earns $2$ bonus points;
*  After buying the sixth item $S = 11$, this increases loyalty level to $5$ and earns $2$ bonus points;
*  After buying the seventh item $S = 12$, this increases loyalty level to $6$ and earns $1$ bonus point;
*  After buying the eighth item $S = 13$;
*  After buying the ninth item $S = 14$, this increases loyalty level to $7$ and earns $1$ bonus point;
*  After buying the tenth item $S = 15$.Overall we got $12$ bonus points.

In the second test case:

*  After buying the first four items $S = 8$, loyalty level is 0;
*  After buying the last item $S = 13$, this increases loyalty level to $1$ and earns $5$ bonus points.In the third test case:

*  After buying the first eight items $S = 20$, loyalty level is 0;
*  After buying the ninth item $S = 30$, this increases loyalty level to $1$ and earns $10$ bonus points;
*  After buying the tenth item $S = 51$, this increases loyalty level to $2$ and earns $21$ bonus points;
*  After buying the eleventh item $S = 73$, this increases loyalty level to $3$ and earns $22$ bonus points.

### Sample Input
```
7
10 2
1 2 1 2 1 2 1 2 1 2
5 10
2 2 2 2 5
11 23
5 5 22 1 21 2 10 3 1 1 2
1 1
1
1 17
11
3 100
44 32 1
16 100500
42801 73112 95296 68791 42217 21871 29316 84405 24273 42894 63370 53473 57156 61369 80 27290
```

### Sample Output
```
12
1 2 2 2 2 2 1 1 1 1
5
2 2 2 2 5
53
1 1 5 2 1 2 5 3 10 21 22
1
1
0
11
0
44 32 1
503499
53473 42894 80 57156 42801 61369 42217 63370 29316 68791 27290 73112 24273 84405 21871 95296
```

---

## Submitted Code

```java

```

---

## Problem Tags
- constructive algorithms
- greedy
- sortings
- two pointers
