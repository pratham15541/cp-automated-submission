
# Stable Subarrays With Equal Boundary and Interior Sum (Medium)

**Platform:** LeetCode  

**Author:** Pratham Parikh (pratham15541)  

**Submitted at:** 10/26/2025, 3:42:22 AM

**Language:** Java  

**Runtime:** 84 ms 

**Memory:** 70.2 MB  

**Problem URL:** [https://leetcode.com/problems/stable-subarrays-with-equal-boundary-and-interior-sum/](https://leetcode.com/problems/stable-subarrays-with-equal-boundary-and-interior-sum/)  

**Submission URL:** [https://leetcode.com/submissions/detail/1811836115/](https://leetcode.com/submissions/detail/1811836115/)  

---

## Problem Statement
<p>You are given an integer array <code>capacity</code>.</p>

<p>A <span data-keyword="subarray-nonempty">subarray</span> <code>capacity[l..r]</code> is considered <strong>stable</strong> if:</p>

<ul>
	<li>Its length is <strong>at least</strong> 3.</li>
	<li>The <strong>first</strong> and <strong>last</strong> elements are each equal to the <strong>sum</strong> of all elements <strong>strictly between</strong> them (i.e., <code>capacity[l] = capacity[r] = capacity[l + 1] + capacity[l + 2] + ... + capacity[r - 1]</code>).</li>
</ul>

<p>Return an integer denoting the number of <strong>stable subarrays</strong>.</p>

<p>&nbsp;</p>
<p><strong class="example">Example 1:</strong></p>

<div class="example-block">
<p><strong>Input:</strong> <span class="example-io">capacity = [9,3,3,3,9]</span></p>

<p><strong>Output:</strong> <span class="example-io">2</span></p>

<p><strong>Explanation:</strong></p>

<ul>
	<li><code>[9,3,3,3,9]</code> is stable because the first and last elements are both 9, and the sum of the elements strictly between them is <code>3 + 3 + 3 = 9</code>.</li>
	<li><code>[3,3,3]</code> is stable because the first and last elements are both 3, and the sum of the elements strictly between them is 3.</li>
</ul>
</div>

<p><strong class="example">Example 2:</strong></p>

<div class="example-block">
<p><strong>Input:</strong> <span class="example-io">capacity = [1,2,3,4,5]</span></p>

<p><strong>Output:</strong> <span class="example-io">0</span></p>

<p><strong>Explanation:</strong></p>

<p>No subarray of length at least 3 has equal first and last elements, so the answer is 0.</p>
</div>

<p><strong class="example">Example 3:</strong></p>

<div class="example-block">
<p><strong>Input:</strong> <span class="example-io">capacity = [-4,4,0,0,-8,-4]</span></p>

<p><strong>Output:</strong> <span class="example-io">1</span></p>

<p><strong>Explanation:</strong></p>

<p><code>[-4,4,0,0,-8,-4]</code> is stable because the first and last elements are both -4, and the sum of the elements strictly between them is <code>4 + 0 + 0 + (-8) = -4</code></p>
</div>

<p>&nbsp;</p>
<p><strong>Constraints:</strong></p>

<ul>
	<li><code>3 &lt;= capacity.length &lt;= 10<sup>5</sup></code></li>
	<li><code>-10<sup>9</sup> &lt;= capacity[i] &lt;= 10<sup>9</sup></code></li>
</ul>


---

## Submitted Code
```java
class Solution {
    public long countStableSubarrays(int[] capacity) {
        int N = capacity.length;
        if (N < 3) return 0;

   
        long[] prefixSum = new long[N + 1];
        prefixSum[0] = 0;
        for (int i = 0; i < N; i++) {
            prefixSum[i + 1] = prefixSum[i] + capacity[i];
        }

        long count = 0;

        Map<Long, Map<Long, Integer>> boundaryToPrefixCount = new HashMap<>();

  
        for (int r = 2; r < N; r++) {
            
          
            int l = r - 2;
            long l_val = capacity[l];
            long l_prefix_minus_1 = prefixSum[l]; 
            
            boundaryToPrefixCount
                .computeIfAbsent(l_val, k -> new HashMap<>())
                .merge(l_prefix_minus_1, 1, Integer::sum);

            long X = capacity[r];
            long P_r = prefixSum[r + 1]; 
            long targetP_l_minus_1 = P_r - 3 * X;

            if (boundaryToPrefixCount.containsKey(X)) {
                Map<Long, Integer> prefixCounts = boundaryToPrefixCount.get(X);
                count += prefixCounts.getOrDefault(targetP_l_minus_1, 0);
            }
        }

        return count;
    }
}
```
