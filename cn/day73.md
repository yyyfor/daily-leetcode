###question
https://leetcode.cn/problems/global-and-local-inversions/
###Solution
```
class Solution {
    public boolean isIdealPermutation(int[] nums) {
        for(int i = 2 ; i < nums.length; i++) {
            if(nums[i] < nums[i - 2] || nums[i] < nums[0]) return false;
            if(i > 2 && nums[i] < nums[1]) return false;
        }
        return true;
    }
}
```

###Conclustion
Runtime beat 99%
Memory beat 36%

###Related Topic
Array, Math