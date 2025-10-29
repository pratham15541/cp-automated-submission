
# Buttons (800)

**Platform:** Codeforces  

**Author:** pratham15541  

**Submitted at:** 25/10/2025, 3:26:07 pm  

**Language:** Java 21  

**Verdict:** OK  

**Time:** 312 ms  

**Memory:** 800.0 KB  

**Problem URL:** [https://codeforces.com/problemset/problem/1858/A](https://codeforces.com/problemset/problem/1858/A)  

**Submission URL:** [https://codeforces.com/contest/1858/submission/345723664](https://codeforces.com/contest/1858/submission/345723664)  

---

## Problem Statement
Anna and Katie ended up in a secret laboratory.

There are $a+b+c$ buttons in the laboratory. It turned out that $a$ buttons can only be pressed by Anna, $b$ buttons can only be pressed by Katie, and $c$ buttons can be pressed by either of them. Anna and Katie decided to play a game, taking turns pressing these buttons. Anna makes the first turn. Each button can be pressed at most once, so at some point, one of the girls will not be able to make her turn.

The girl who cannot press a button loses. Determine who will win if both girls play optimally.

ExampleNoteFor the simplicity of the explanation, we will numerate the buttons by the numbers from $1$ to $a+b+c$: the first $a$ buttons can only be pressed by Anna, the next $b$ buttons can only be pressed by Katie, and the last $c$ buttons can be pressed by either of them.

In the first test case, Anna can press the $3$-rd button on the first turn. Then Katie will press the $2$-nd button (since it is the only possible turn for her). Then Anna will press the $1$-st button. Katie won't have a button to press, so Anna will win.

In the second test case, Anna can press the first nine buttons in some order on her turns. No matter what buttons Katie will press, all the buttons from the $10$-th to the $15$-th will be pressed after $12$ turns. On the $13$-th turn, Anna will press one of the first nine buttons and Katie will not have a button to press on her turn. Thus, Anna will win.

In the third test case, the game can proceed as follows: 

 
*  On the $1$-st turn Anna presses the $5$-th button. 
*  On the $2$-st turn Katie presses the $4$-th button. 
*  On the $3$-st turn Anna presses the $6$-th button. 
*  On the $4$-st turn Katie presses the $3$-th button. 
*  On the $5$-st turn Anna presses the $1$-th button. 
*  On the $6$-st turn Katie presses the $2$-th button. 
*  Anna cannot make the turn, so Katie wins. It can be shown that Katie can win no matter what moves Anna takes.

### Sample Input
```
51 1 19 3 31 2 36 6 92 2 8
```

### Sample Output
```
First
First
Second
First
Second
```

---

## Submitted Code
(Your solution code goes here)

---

## Problem Tags
- games
- greedy
- math
