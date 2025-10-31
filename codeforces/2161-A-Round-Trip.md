
# Round Trip (Unrated)

**Platform:** Codeforces  

**Author:** pratham15541  

**Submitted at:** 10/30/2025, 5:13:53 PM  

**Language:** Java 21  

**Verdict:** OK  

**Time:** 296 ms  

**Memory:** 2100.0 KB  

**Problem URL:** [https://codeforces.com/problemset/problem/2161/A](https://codeforces.com/problemset/problem/2161/A)  

**Submission URL:** [https://codeforces.com/contest/2161/submission/346688105](https://codeforces.com/contest/2161/submission/346688105)  

---

## Problem Statement
They say that if you do 1000 rounds, there's a secret cartoon in the end (c) Petya and Vasya love participating in Codeforces contests. Vasya made a bet with Petya that he will take part in more rated rounds than him. Initially, Vasya's rating is $R_0$. There will be $n$ rounds conducted in total, each of one of two types: 

 
*  div. 1&nbsp;— rated for all participants 
*  div. 2&nbsp;— rated for participants with rating strictly less than $X$, and unrated for all others,  In an unrated round, Vasya cannot change his rating. If Vasya's rating before a rated round was $R$, then for any non-negative integer $x$ between $R-D$ and $R+D$ (inclusive) Vasya can adopt a strategy such that his rating becomes exactly $x$ afterwards (here $D$ is a positive integer). Note that rating may never become negative.

Help Vasya determine the maximum number of rated rounds he can participate in.

ExampleNoteIn the first example, since $R_0 \geq X$, each div. 2 round is unrated for Vasya, so his rating never changes. Therefore, he cannot make any round rated for himself, and the answer is $0$.

In the second example, one of the optimal sequences of ratings after each round is: $2098 \rightarrow 2103 \rightarrow 2101 \rightarrow 2099 \rightarrow 2097 \rightarrow 2097 \rightarrow 2092$.

### Sample Input
```
4
2100 2100 5 3
222
2098 2100 5 6
111211
2115 2100 226 7
2211121
0 10 4 8
22111121
```

### Sample Output
```
0
6
5
8
```

---

## Submitted Code

```java

```

---

## Problem Tags
- greedy
- implementation
