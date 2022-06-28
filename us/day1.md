###question
https://leetcode.com/problems/minimum-deletions-to-make-character-frequencies-unique/

###Solution
```
class Solution {
    public int minDeletions(String s) {
        int [] dp = new int [26];
        for(char ch : s.toCharArray()) {
            dp[ch - 'a']++;
        }
        Set<Integer> set = new HashSet();
        int count = 0;
        for(int i = 0 ; i < 26; i++) {
            if(dp[i] == 0) continue;
            while(set.contains(dp[i]) && dp[i] > 0) {
                count++;
                dp[i]--;
            } 
            set.add(dp[i]);
        }
        return count;
    }
}
```

###Conclustion
Runtime beat 97.72%
Memory beat 80.86%

###Related Topic
String, Greedy, Sorting