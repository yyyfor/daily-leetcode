###question
https://leetcode.cn/problems/maximum-product-of-two-elements-in-an-array/submissions/
###Solution
```
class Solution {
    public int maxProduct(int[] nums) {
        int max1 = 0;
        int max2 = 0;
        for(int num : nums) {
            if(num > max1) {
                max2 = max1;
                max1 = num;
            } else if(num > max2) {
                max2 = num;
            }
        }
        return (max1 - 1) * (max2 - 1);
    }
}
```

there is better hash solution

###Conclustion
Runtime beat 100%
Memory beat 72%

###Related Topic
Array, Sorting