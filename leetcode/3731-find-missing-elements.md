
# Find Missing Elements (Easy)

**Platform:** LeetCode  

**Author:** Pratham Parikh (pratham15541)  

**Submitted at:** 11/2/2025, 2:51:58 AM

**Language:** Java  

**Runtime:** 7 ms 

**Memory:** 47.1 MB  

**Problem URL:** [https://leetcode.com/problems/find-missing-elements/](https://leetcode.com/problems/find-missing-elements/)  

**Submission URL:** [https://leetcode.com/submissions/detail/1818197339/](https://leetcode.com/submissions/detail/1818197339/)  

---

## Problem Statement
<p>You are given an integer array <code>nums</code> consisting of <strong>unique</strong> integers.</p>

<p>Originally, <code>nums</code> contained <strong>every integer</strong> within a certain range. However, some integers might have gone <strong>missing</strong> from the array.</p>

<p>The <strong>smallest</strong> and <strong>largest</strong> integers of the original range are still present in <code>nums</code>.</p>

<p>Return a <strong>sorted</strong> list of all the missing integers in this range. If no integers are missing, return an <strong>empty</strong> list.</p>

<p>&nbsp;</p>
<p><strong class="example">Example 1:</strong></p>

<div class="example-block">
<p><strong>Input:</strong> <span class="example-io">nums = [1,4,2,5]</span></p>

<p><strong>Output:</strong> <span class="example-io">[3]</span></p>

<p><strong>Explanation:</strong></p>

<p>The smallest integer is 1 and the largest is 5, so the full range should be <code>[1,2,3,4,5]</code>. Among these, only 3 is missing.</p>
</div>

<p><strong class="example">Example 2:</strong></p>

<div class="example-block">
<p><strong>Input:</strong> <span class="example-io">nums = [7,8,6,9]</span></p>

<p><strong>Output:</strong> <span class="example-io">[]</span></p>

<p><strong>Explanation:</strong></p>

<p>The smallest integer is 6 and the largest is 9, so the full range is <code>[6,7,8,9]</code>. All integers are already present, so no integer is missing.</p>
</div>

<p><strong class="example">Example 3:</strong></p>

<div class="example-block">
<p><strong>Input:</strong> <span class="example-io">nums = [5,1]</span></p>

<p><strong>Output:</strong> <span class="example-io">[2,3,4]</span></p>

<p><strong>Explanation:</strong></p>

<p>The smallest integer is 1 and the largest is 5, so the full range should be <code>[1,2,3,4,5]</code>. The missing integers are 2, 3, and 4.</p>
</div>

<p>&nbsp;</p>
<p><strong>Constraints:</strong></p>

<ul>
	<li><code>2 &lt;= nums.length &lt;= 100</code></li>
	<li><code>1 &lt;= nums[i] &lt;= 100</code></li>
</ul>


---

## Submitted Code
```java
class Solution {
    public List<Integer> findMissingElements(int[] nums) {
        Arrays.sort(nums);
        int max = nums[nums.length-1];
        int min = nums[0];
        int loop = max-min;
        List<Integer> ans = new ArrayList<>();
            int i = 1;
        Set<Integer> set = new HashSet<>();
        for (int n : nums) set.add(n);
        
        for (int x = min; x <= max; x++) {
            if (!set.contains(x)) ans.add(x);
        }
        return ans;
    }
}
```
