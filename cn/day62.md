###question
https://leetcode.cn/problems/score-of-parentheses/
###Solution
```
class Solution {
    public int scoreOfParentheses(String s) {
        int l = s.length();
        int sum = 0;
        int n = 0;
        for(int i = 0 ; i < l; i++) {
            char ch = s.charAt(i);
            if(ch == '(') {
                if(n == 0) {
                    n = 1;
                } else {
                    n *= 2;
                }
            }
            if(ch == ')') {
                if(s.charAt(i - 1) == '(') {
                    sum += n;
                }
                n /= 2;
            }
        }
        return sum;
    }
}
```
multiple ( by 2

###Conclustion
Runtime beat 100%
Memory beat 39%

###Related Topic
String