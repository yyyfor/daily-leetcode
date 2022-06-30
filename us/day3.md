###question
https://leetcode.com/problems/minimum-moves-to-equal-array-elements-ii/
###Solution
```
class Solution {
    public int minMoves2(int[] nums) {
        Arrays.sort(nums);
        int count = 0;
        int start = 0;
        int end = nums.length - 1;
        while(start < end) {
            count += nums[end] - nums[start];
            start++;
            end--;
        }
        return count;
    }
}
```

###Conclustion
Runtime beat 66%
Memory beat 75%
先排序，算出两端到中间值的差值相加

###Related Topic
Array, Sorting, Math