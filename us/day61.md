###question
https://leetcode.com/problems/3sum-closest/
###Solution
```
class Solution {
    public int threeSumClosest(int[] nums, int target) {
        Arrays.sort(nums);
        int max = Integer.MAX_VALUE;
        int result = 0;
        for(int i = 0 ; i < nums.length - 2; i++) {
            int j = i + 1;
            int m = nums.length - 1;
            while(j < m) {
                int sum = nums[i] + nums[j] + nums[m];
                if(sum == target) return sum;
                if(Math.abs(sum - target) < max) {
                    result = sum;
                    max = Math.abs(sum - target);
                }
                if(sum < target) {
                    j++;
                } else {
                    m--;
                }
            }
               
        }
        return result;
    }
}
```
no need third loop. Use two pointer

###Conclustion
Runtime beat 96%
Memory beat 85%

###Related Topic
Sorting, Array, Two pointer