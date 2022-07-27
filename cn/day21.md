###question
https://leetcode.cn/problems/best-team-with-no-conflicts
###Solution
```
class Solution {
    public int bestTeamScore(int[] scores, int[] ages) {
        int [][] array = new int [scores.length][2];
        for(int i = 0 ; i < scores.length; i++) {
            array[i][0] = scores[i];
            array[i][1] = ages[i];
        }

        Arrays.sort(array, (o1, o2) -> o1[1] == o2[1] ? o1[0] - o2[0]:
        o1[1] - o2[1]);

        int [] dp = new int [scores.length];
        for(int i = 0 ; i < scores.length; i++) {
            dp[i] = array[i][0];
            for(int j = 0; j < i; j++) {
                if(array[j][0] <= array[i][0]) {
                    dp[i] = Math.max(dp[i], dp[j] + array[i][0]);
                }
            }
        } 
        int max = 0;
        for(int num : dp) {
            max = Math.max(max, num);
        }
        return max;
    }
}
```

###Conclustion
Runtime beat 54%
Memory beat 8%

###Related Topic
Array, DP, sorting