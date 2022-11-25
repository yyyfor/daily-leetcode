###question
https://leetcode.cn/problems/maximum-nesting-depth-of-the-parentheses/description/
###Solution
```
class Solution {
    public int maxDepth(String s) {
        Stack<Character> stack = new Stack();
        int max = 0;
        for(int i = 0 ; i < s.length(); i++) {
            char ch = s.charAt(i);
            if(ch == '(') {
                stack.push('(');
                max = Math.max(max, stack.size());
            }
            if(ch == ')') {
                stack.pop();
            }
        }
        return max;
    }
}
```
###Conclustion
Runtime beat 33%
Memory beat 14%

###Related Topic
Stack