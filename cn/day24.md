###question
https://leetcode.cn/problems/maximum-product-subarray/submissions/
###Solution
```
class Solution {
    public int maxProduct(int[] nums) {
        int max = nums[0];
        int m = nums[0];
        int n = nums[0];
        for(int i = 1; i < nums.length; i++) {
            if(nums[i] < 0) {
                int tmp = m;
                m = n;
                n = tmp;
            }
            m = Math.max(nums[i], m * nums[i]);
            n = Math.min(nums[i], n * nums[i]);
            max = Math.max(m, max);
        }
        return max;

    }
}
```

###Conclustion
Runtime beat 95%
Memory beat 70%

###Related Topic
Array, DP