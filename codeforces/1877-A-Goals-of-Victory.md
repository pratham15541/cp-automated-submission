
# Goals of Victory (800)

**Platform:** Codeforces  

**Author:** pratham15541  

**Submitted at:** 10/23/2025, 8:33:51 AM  

**Language:** Java 21  

**Verdict:** OK  

**Time:** 234 ms  

**Memory:** 700.0 KB  

**Problem URL:** [https://codeforces.com/problemset/problem/1877/A](https://codeforces.com/problemset/problem/1877/A)  

**Submission URL:** [https://codeforces.com/contest/1877/submission/345307534](https://codeforces.com/contest/1877/submission/345307534)  

---

## Problem Statement
There are $n$ teams in a football tournament. Each pair of teams match up once. After every match, Pak Chanek receives two integers as the result of the match, the number of goals the two teams score during the match. The efficiency of a team is equal to the total number of goals the team scores in each of its matches minus the total number of goals scored by the opponent in each of its matches.

After the tournament ends, Pak Dengklek counts the efficiency of every team. Turns out that he forgot about the efficiency of one of the teams. Given the efficiency of $n-1$ teams $a_1,a_2,a_3,\ldots,a_{n-1}$. What is the efficiency of the missing team? It can be shown that the efficiency of the missing team can be uniquely determined.

ExampleNoteIn the first test case, below is a possible tournament result: 

 
*  Team $1$ vs. Team $2$: $1-2$ 
*  Team $1$ vs. Team $3$: $3-0$ 
*  Team $1$ vs. Team $4$: $3-2$ 
*  Team $2$ vs. Team $3$: $1-4$ 
*  Team $2$ vs. Team $4$: $1-3$ 
*  Team $3$ vs. Team $4$: $5-0$ The efficiency of each team is: 

 
*  Team $1$: $(1+3+3)-(2+0+2)=7-4=3$ 
*  Team $2$: $(2+1+1)-(1+4+3)=4-8=-4$ 
*  Team $3$: $(0+4+5)-(3+1+0)=9-4=5$ 
*  Team $4$: $(2+3+0)-(3+1+5)=5-9=-4$ Therefore, the efficiency of the missing team (team $4$) is $-4$.

It can be shown that any possible tournament of $4$ teams that has the efficiency of $3$ teams be $3$, $-4$, and $5$ will always have the efficiency of the $4$-th team be $-4$.

---

## Submitted Code
(Your solution code goes here)

---

## Problem Tags
- math
