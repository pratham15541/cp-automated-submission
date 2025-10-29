
# Maximum Alternating Sum of Squares (Medium)

**Platform:** LeetCode  

**Author:** Pratham Parikh (pratham15541)  

**Submitted at:** 10/26/2025, 3:24:13 AM

**Language:** Java  

**Runtime:** 29 ms 

**Memory:** 60.8 MB  

**Problem URL:** [https://leetcode.com/problems/maximum-alternating-sum-of-squares/](https://leetcode.com/problems/maximum-alternating-sum-of-squares/)  

**Submission URL:** [https://leetcode.com/submissions/detail/1811813141/](https://leetcode.com/submissions/detail/1811813141/)  

---

## Problem Statement
<p>You are given an integer array <code>nums</code>. You may <strong>rearrange the elements</strong> in any order.</p>

<p>The <strong>alternating score</strong> of an array <code>arr</code> is defined as:</p>

<ul>
	<li><code>score = arr[0]<sup>2</sup> - arr[1]<sup>2</sup> + arr[2]<sup>2</sup> - arr[3]<sup>2</sup> + ...</code></li>
</ul>

<p>Return an integer denoting the <strong>maximum possible alternating score</strong> of <code>nums</code> after rearranging its elements.</p>

<p>&nbsp;</p>
<p><strong class="example">Example 1:</strong></p>

<div class="example-block">
<p><strong>Input:</strong> <span class="example-io">nums = [1,2,3]</span></p>

<p><strong>Output:</strong> <span class="example-io">12</span></p>

<p><strong>Explanation:</strong></p>

<p>A possible rearrangement for <code>nums</code> is <code>[2,1,3]</code>, which gives the maximum alternating score among all possible rearrangements.</p>

<p>The alternating score is calculated as:</p>

<p><code>score = 2<sup>2</sup> - 1<sup>2</sup> + 3<sup>2</sup> = 4 - 1 + 9 = 12</code></p>
</div>

<p><strong class="example">Example 2:</strong></p>

<div class="example-block">
<p><strong>Input:</strong> <span class="example-io">nums = [1,-1,2,-2,3,-3]</span></p>

<p><strong>Output:</strong> <span class="example-io">16</span></p>

<p><strong>Explanation:</strong></p>

<p>A possible rearrangement for <code>nums</code> is <code>[-3,-1,-2,1,3,2]</code>, which gives the maximum alternating score among all possible rearrangements.</p>

<p>The alternating score is calculated as:</p>

<p><code>score = (-3)<sup>2</sup> - (-1)<sup>2</sup> + (-2)<sup>2</sup> - (1)<sup>2</sup> + (3)<sup>2</sup> - (2)<sup>2</sup> = 9 - 1 + 4 - 1 + 9 - 4 = 16</code></p>
</div>

<p>&nbsp;</p>
<p><strong>Constraints:</strong></p>

<ul>
	<li><code>1 &lt;= nums.length &lt;= 10<sup>5</sup></code></li>
	<li><code>-4 * 10<sup>4</sup> &lt;= nums[i] &lt;= 4 * 10<sup>4</sup></code></li>
</ul>


---

## Submitted Code
```java
class Solution {
    public long maxAlternatingSum(int[] nums) {
        long[] squares = new long[nums.length];
        for(int i=0;i<nums.length;i++){
            squares[i] = nums[i] * nums[i];
        }
        Arrays.sort(squares);
        int n = squares.length;
        long sum1 =0, sum2 =0;
        int sum1Term = (n+1)/2;
        int sum2Term = n/2;
        for(int i =0;i<sum1Term;i++){
            sum1+= squares[n-1-i];
        }
        for(int i=0;i<sum2Term;i++){
            sum2+= squares[i];
        }
        return sum1-sum2;
    }
}
```
