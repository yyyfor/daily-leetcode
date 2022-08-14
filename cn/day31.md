###question
https://leetcode.cn/problems/maximum-score-after-splitting-a-string/submissions/
###Solution
```
class Solution {
    public int maxScore(String s) {
        int left = s.charAt(0) == '0'? 1 : 0;
        int right = s.charAt(s.length() - 1) == '1' ? 1 : 0;
        for(int i = 1; i < s.length() - 1; i++) {
            if(s.charAt(i) == '1') right++;
        }
        int max = left + right;
        for(int i = 1; i < s.length() - 1; i++) {
            if(s.charAt(i) == '0') {
                left++;
            }
            if(s.charAt(i) == '1') {
                right--;
            }
            max = Math.max(left + right, max);
        }
        return max;
    }
}
```

###Conclustion
Runtime beat 94%
Memory beat 72%

###Related Topic
String