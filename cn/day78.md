###question
https://leetcode.cn/problems/number-of-subarrays-with-bounded-maximum/discussion/
###Solution
```
class Solution {
    public int numSubarrayBoundedMax(int[] nums, int left, int right) {
        int last1 = -1;
        int last2 = -1;
        int sum = 0;
        for(int i = 0 ; i < nums.length; i++) {
            int num = nums[i];
            if(num >= left && num <= right) {
                last1 = i;
            }
            if(num > right) {
                last2 = i;
                last1 = -1;
            }
            if(last1 != - 1) {
                sum += last1 - last2;
            }
        }
        return sum;
    }
}
```
###Conclustion
Runtime beat 90%
Memory beat 56%

###Related Topic
Array, two pointer