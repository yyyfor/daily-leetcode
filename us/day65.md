###question
https://leetcode.com/problems/largest-perimeter-triangle/submissions/
###Solution
```
class Solution {
    public int largestPerimeter(int[] nums) {
        Arrays.sort(nums);
        for(int i = nums.length - 1; i >= 2; i--) {
            if(nums[i] < nums[i-1] + nums[i-2]) return nums[i] + nums[i-1] + nums[i-2];
        }
        return 0;
    }
}
```

###Conclustion
Runtime beat 99%
Memory beat 98%

###Related Topic
Array, Sorting, Greedy