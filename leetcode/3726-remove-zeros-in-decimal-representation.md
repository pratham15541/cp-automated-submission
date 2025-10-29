
# Remove Zeros in Decimal Representation (Easy)

**Platform:** LeetCode  

**Author:** Pratham Parikh (pratham15541)  

**Submitted at:** 10/26/2025, 3:06:00 AM

**Language:** Java  

**Runtime:** 2 ms 

**Memory:** 41.4 MB  

**Problem URL:** [https://leetcode.com/problems/remove-zeros-in-decimal-representation/](https://leetcode.com/problems/remove-zeros-in-decimal-representation/)  

**Submission URL:** [https://leetcode.com/submissions/detail/1811788227/](https://leetcode.com/submissions/detail/1811788227/)  

---

## Problem Statement
<p>You are given a <strong>positive</strong> integer <code>n</code>.</p>

<p>Return the integer obtained by removing all zeros from the decimal representation of <code>n</code>.</p>

<p>&nbsp;</p>
<p><strong class="example">Example 1:</strong></p>

<div class="example-block">
<p><strong>Input:</strong> <span class="example-io">n = 1020030</span></p>

<p><strong>Output:</strong> <span class="example-io">123</span></p>

<p><strong>Explanation:</strong></p>

<p>After removing all zeros from 1<strong><u>0</u></strong>2<strong><u>00</u></strong>3<strong><u>0</u></strong>, we get 123.</p>
</div>

<p><strong class="example">Example 2:</strong></p>

<div class="example-block">
<p><strong>Input:</strong> <span class="example-io">n = 1</span></p>

<p><strong>Output:</strong> <span class="example-io">1</span></p>

<p><strong>Explanation:</strong></p>

<p>1 has no zero in its decimal representation. Therefore, the answer is 1.</p>
</div>

<p>&nbsp;</p>
<p><strong>Constraints:</strong></p>

<ul>
	<li><code>1 &lt;= n &lt;= 10<sup>15</sup></code></li>
</ul>


---

## Submitted Code
```java
class Solution {
    public long removeZeros(long n) {
        String val = String.valueOf(n);
        StringBuilder sb = new StringBuilder();
        for(char c : val.toCharArray()){
            if(c == '0') continue;
            sb.append(c);
        }
        String ans = sb.toString();
        return Long.parseLong(ans);
    }
}
```
