###question
https://leetcode.com/problems/increasing-triplet-subsequence/submissions/
###Solution
```
class Solution {
    public boolean increasingTriplet(int[] nums) {
        int small = Integer.MAX_VALUE;
        int big = Integer.MAX_VALUE;
        for(int num : nums) {
            if(num <= small) {
                small = num;
            } else if(num <= big) {
                big = num;
            } else return true;
        }
        return false;
    }
}
```

###Conclustion
Runtime beat 27%
Memory beat 62%

###Related Topic
Array, Greedy