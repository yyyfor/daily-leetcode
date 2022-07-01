###question
https://leetcode.cn/problems/different-ways-to-add-parentheses/
###Solution
```
class Solution {
    Map<String, List<Integer>> map = new HashMap();
    public List<Integer> diffWaysToCompute(String expression) {
        if(map.containsKey(expression)) return map.get(expression);
        List<Integer> list = new ArrayList();
        for(int i = 0 ; i < expression.length(); i++) {
            char ch = expression.charAt(i);
            if(ch == '+' || ch == '-' || ch == '*') {
                List<Integer> left = diffWaysToCompute(expression.substring(0, i));
                List<Integer> right = diffWaysToCompute(expression.substring(i + 1));
                for(int i1 : left) {
                    for(int i2 : right) {
                        if(ch == '+') {
                            list.add(i1 + i2);
                        }
                        if(ch == '-') {
                            list.add(i1 - i2);
                        }
                        if(ch == '*') {
                            list.add(i1 * i2);
                        }
                    }
                }
            }
        }
        if(list.size() == 0) list.add(Integer.valueOf(expression));
        map.put(expression, list);
        return list;
    }
}
```

###Conclustion
Runtime beat 99%
Memory beat 85%
参考别人的解答作出，需要递归算出所有表达式结果，然后记录在map里

###Related Topic
Recursion, String, Math, Memoization