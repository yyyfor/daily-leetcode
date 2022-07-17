###question
https://leetcode.cn/problems/array-nesting/
###Solution
```
class Solution {
    int max = 0;
    public int arrayNesting(int[] nums) {
        int [] dp = new int [nums.length];
        for(int i = 0 ; i < nums.length; i++) {
            max = Math.max(max, helper(nums, i, dp, new HashSet<Integer>(),0));
        }
        return max;
    }

    private int helper(int [] nums, int index, int [] dp, Set<Integer> set, int count) {
        if(dp[index] != 0) {
            return dp[index];
        }
        if(set.contains(index)) {
            dp[index] = count;
            return count;
        }
        set.add(index);
        int num = helper(nums, nums[index], dp, set, count + 1);
        dp[index] = num ;
        return num ;
        
        
    }
}
```

###Conclustion
Runtime beat 5%
Memory beat 5%

####better solution
```
public int arrayNesting(int[] nums) {
        int max = 1;
        for(int i = 0; i < nums.length; i++){
            if(max > nums.length/2)
                return max;
            int curMax = 1;
            int cur = nums[nums[i]];
            while(nums[i] != cur){
                curMax++;
                cur = nums[cur];
            }
            max = curMax > max? curMax : max;
        }
        return max;
    }
```

###Related Topic
Array, DFS