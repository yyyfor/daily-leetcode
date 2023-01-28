###question
https://leetcode.cn/problems/ways-to-make-a-fair-array/description/
###Solution
```
class Solution {
    public int waysToMakeFair(int[] nums) {
        int a = 0;
        int b = 0;
        int c = 0;
        int d = 0;
        for(int i = 0 ; i < nums.length; i++) {
            if(i % 2 == 0) {
                a += nums[i];
            } else {
                b += nums[i];
            }
        }
        int count = 0;
        for(int i = 0 ; i < nums.length; i++) {
            if(i % 2 == 0) {
                a -= nums[i];
            } else {
                b -= nums[i];
            }
            if(a + d == b + c) count++;
            if(i % 2 == 0) {
                c += nums[i];
            } else {
                d += nums[i];
            }
        }
        return count;
    }
}
```


###Conclustion
Runtime beat 85%
Memory beat 42%

###Related Topic
DP