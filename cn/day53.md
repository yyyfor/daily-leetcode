###question
https://leetcode.cn/problems/crawler-log-folder/
###Solution
```
class Solution {
    public int minOperations(String[] logs) {
        Stack<String> stack = new Stack();
        for(String log: logs) {
            log = log.substring(0, log.length() - 1);
            System.out.println(log);
            if(log.equals(".")) continue;
            else if(log.equals("..")) {
                if(!stack.isEmpty()) stack.pop();
            } 
            else {
                stack.push(log);
            }
        }
        return stack.size();
    }
}
```

###Conclustion
Runtime beat 21%
Memory beat 49%

###Related Topic
Stack, String