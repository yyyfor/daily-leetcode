###question
https://leetcode.com/problems/maximum-length-of-repeated-subarray/
###Solution
```
class Solution {
    public int findLength(int[] nums1, int[] nums2) {
        int m = nums1.length;
        int n = nums2.length;
        int [][] dp = new int [m][n];
        int max = 0;
        for(int i = 0 ; i < m; i++) {
            for(int j = 0 ; j < n; j++) {
                if(nums1[i] == nums2[j]) {
                    if(i == 0 || j == 0) dp[i][j] = 1;
                    else dp[i][j] = dp[i-1][j-1] + 1;
                    max = Math.max(max, dp[i][j]);
                }
            }
        }
        return max;
    }
}
```

###Conclustion
Runtime beat 19%
Memory beat 68%

###Related Topic
DP