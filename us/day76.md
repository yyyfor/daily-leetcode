###question
https://leetcode.com/problems/perfect-squares/
###Solution
```
class Solution {
    public int numSquares(int n) {
        List<Integer> list = new ArrayList();
        for(int i = 1 ; i * i <= n; i++) {
            list.add(i * i);
        }
        int [] dp = new int [n + 1];
        Arrays.fill(dp, Integer.MAX_VALUE);
        dp[0] = 0;
        for(int i = list.size() - 1; i >= 0; i--) {
            int num = list.get(i);
            System.out.println(num);
            for(int j = num;  j <= n; j++) {
                if(dp[j - num] != Integer.MAX_VALUE || (j - num == 0)) {
                    dp[j] = Math.min(dp[j], dp[j - num] + 1);
                }
            }
        }
        return dp[n];
    }
}
```
###Conclustion
Runtime beat 45%
Memory beat 27%

###Related Topic
DP