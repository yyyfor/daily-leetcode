###question
https://leetcode.cn/problems/partition-array-into-disjoint-intervals/
###Solution
```
class Solution {
    public int partitionDisjoint(int[] nums) {
        int lMax = nums[0];
        int max = nums[0];
        int index = 0;
        for(int i = 1; i < nums.length; i++) {
            if(nums[i] < lMax) {
                index = i;
                lMax = max;
            }
            max = Math.max(max, nums[i]);
        }
        return index + 1;
    }
}
```

###Conclustion
Runtime beat 92%
Memory beat 71%

###Related Topic
Array