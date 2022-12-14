###question
https://leetcode.com/problems/house-robber/description/
###Solution
```
class Solution {
    public int rob(int[] nums) {
        if(nums.length == 1) return nums[0];
        if(nums.length == 2) return Math.max(nums[0], nums[1]);
        int l = nums.length - 1;
        for(int i = 2; i <= l; i++) {
            if(i == 2) {
                nums[2] = nums[0] + nums[2];
                continue;
            }
            nums[i] = Math.max(nums[i-2], nums[i-3]) + nums[i];
        }
        return Math.max(nums[l], nums[l - 1]);
    }
}
```


###Conclustion
Runtime beat 100%
Memory beat 84%

###Related Topic
DP