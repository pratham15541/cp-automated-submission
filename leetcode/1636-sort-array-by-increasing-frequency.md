
# Sort Array by Increasing Frequency (Easy)

**Platform:** LeetCode  

**Author:** Pratham Parikh (pratham15541)  

**Submitted at:** 10/12/2025, 4:45:17 PM

**Language:** Java  

**Runtime:** 6 ms 

**Memory:** 44.4 MB  

**Problem URL:** [https://leetcode.com/problems/sort-array-by-increasing-frequency/](https://leetcode.com/problems/sort-array-by-increasing-frequency/)  

**Submission URL:** [https://leetcode.com/submissions/detail/1799532385/](https://leetcode.com/submissions/detail/1799532385/)  

---

## Problem Statement
<p>Given an array of integers <code>nums</code>, sort the array in <strong>increasing</strong> order based on the frequency of the values. If multiple values have the same frequency, sort them in <strong>decreasing</strong> order.</p>

<p>Return the <em>sorted array</em>.</p>

<p>&nbsp;</p>
<p><strong class="example">Example 1:</strong></p>

<pre>
<strong>Input:</strong> nums = [1,1,2,2,2,3]
<strong>Output:</strong> [3,1,1,2,2,2]
<strong>Explanation:</strong> &#39;3&#39; has a frequency of 1, &#39;1&#39; has a frequency of 2, and &#39;2&#39; has a frequency of 3.
</pre>

<p><strong class="example">Example 2:</strong></p>

<pre>
<strong>Input:</strong> nums = [2,3,1,3,2]
<strong>Output:</strong> [1,3,3,2,2]
<strong>Explanation:</strong> &#39;2&#39; and &#39;3&#39; both have a frequency of 2, so they are sorted in decreasing order.
</pre>

<p><strong class="example">Example 3:</strong></p>

<pre>
<strong>Input:</strong> nums = [-1,1,-6,4,5,-6,1,4,1]
<strong>Output:</strong> [5,-1,4,4,-6,-6,1,1,1]</pre>

<p>&nbsp;</p>
<p><strong>Constraints:</strong></p>

<ul>
	<li><code>1 &lt;= nums.length &lt;= 100</code></li>
	<li><code>-100 &lt;= nums[i] &lt;= 100</code></li>
</ul>


---

## Submitted Code
```java
class Solution {
    public int[] frequencySort(int[] nums) {
        int[] ans = new int[nums.length];
        Map<Integer,Integer> mp = new HashMap<>();
        for(int n:nums){
            mp.put(n, mp.getOrDefault(n,0)+1);
        }
        ArrayList<Integer> list = new ArrayList<>(mp.keySet());
        Collections.sort(list, (a,b) -> {
            if(mp.get(a).equals(mp.get(b))){
                return b-a;  //descending
            }
            return mp.get(a) - mp.get(b);
        });

        int k=0;
        for(Integer n : list){
            int count = mp.get(n);
            while(count>0){
                ans[k++] = n;
                count--;
            }
        }
        return ans;
    }
}
```
