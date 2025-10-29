
# Sequence Game (800)

**Platform:** Codeforces  

**Author:** pratham15541  

**Submitted at:** 25/10/2025, 3:42:35 pm  

**Language:** Java 21  

**Verdict:** OK  

**Time:** 421 ms  

**Memory:** 11200.0 KB  

**Problem URL:** [https://codeforces.com/problemset/problem/1862/B](https://codeforces.com/problemset/problem/1862/B)  

**Submission URL:** [https://codeforces.com/contest/1862/submission/345726028](https://codeforces.com/contest/1862/submission/345726028)  

---

## Problem Statement
Tema and Vika are playing the following game.

First, Vika comes up with a sequence of positive integers $a$ of length $m$ and writes it down on a piece of paper. Then she takes a new piece of paper and writes down the sequence $b$ according to the following rule: 

 
*  First, she writes down $a_1$. 
*  Then, she writes down only those $a_i$ ($2 \le i \le m$) such that $a_{i - 1} \le a_i$. Let the length of this sequence be denoted as $n$. For example, from the sequence $a=[4, 3, 2, 6, 3, 3]$, Vika will obtain the sequence $b=[4, 6, 3]$.

She then gives the piece of paper with the sequence $b$ to Tema. He, in turn, tries to guess the sequence $a$.

Tema considers winning in such a game highly unlikely, but still wants to find at least one sequence $a$ that could have been originally chosen by Vika. Help him and output any such sequence.

Note that the length of the sequence you output should not exceed the input sequence length by more than two times.

ExampleNoteThe first sample is explained in the problem statement.

In the second sample, Vika could have chosen the original sequence.

### Sample Input
```
634 6 331 2 351 7 9 5 7114421 151 2 2 1 1
```

### Sample Output
```
6
4 3 2 6 3 3
3
1 2 3
6
1 7 9 3 5 7
1
144
2
1 1
6
1 2 2 1 1 1
```

---

## Submitted Code
(Your solution code goes here)

---

## Problem Tags
- constructive algorithms
