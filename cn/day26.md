###question
https://leetcode.cn/problems/minimum-value-to-get-positive-step-by-step-sum/submissions/
###Solution
```
class Solution {
    public int minStartValue(int[] nums) {
        int min = Integer.MAX_VALUE;
        int sum = 0;
        for(int i = 0 ; i < nums.length; i++) {
            sum += nums[i];
            min = Math.min(min, sum);
        }
        return Math.max(1, 1 - min);
    }
}
```

###Conclustion
Runtime beat 100%
Memory beat 64%


###Related Topic
Array