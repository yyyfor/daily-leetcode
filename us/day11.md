###question
https://leetcode.com/problems/matchsticks-to-square/
###Solution
```
class Solution {
    public boolean makesquare(int[] matchsticks) {
        int sum = 0;
        for(int match: matchsticks) {
            sum += match;
        }
        if(sum % 4 != 0) return false;
        Arrays.sort(matchsticks);
        return helper(matchsticks.length - 1, new int [4], sum / 4, matchsticks);
    }
    
    private boolean helper(int index, int [] nums, int target, int [] matchsticks) {
        if(index == -1) return true;
        
        for(int i = 0 ; i < 4; i++) {
            if(nums[i] + matchsticks[index] > target) continue;
            nums[i] += matchsticks[index];
            if(helper(index - 1, nums, target, matchsticks)) return true;
            nums[i] -= matchsticks[index];
        }
        return false;
    }
}
```

###Conclustion
Runtime beat 52%
Memory beat 65%
先sort效率会更高，用dfs记录使用过的火柴

###Related Topic
DP, Array