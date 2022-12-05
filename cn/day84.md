###question
https://leetcode.cn/problems/longest-palindromic-subsequence/description/
###Solution
```
class Solution {
    public int longestPalindromeSubseq(String s) {
        int max = 0;
        int l = s.length();
        int [][] dp = new int [l][l];
        for(int i = l - 1 ; i >= 0; i--) {
            dp[i][i] = 1;
            for(int j = i + 1; j < l; j++) {
                if(s.charAt(i) == s.charAt(j)) {
                    dp[i][j] = dp[i + 1][j - 1] + 2;
                } else {
                    dp[i][j] = Math.max(dp[i][j-1], dp[i + 1][j]);
                }
            }
        }
        return dp[0][l-1];
    }
}
```


###Conclustion
Runtime beat 57%
Memory beat 41%

###Related Topic
DP