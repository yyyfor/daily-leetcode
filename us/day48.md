###question
https://leetcode.com/problems/numbers-with-same-consecutive-differences/submissions/
###Solution
```
class Solution {
    public int[] numsSameConsecDiff(int n, int k) {
        List<String> list = new ArrayList();
        StringBuilder sb = new StringBuilder();
        for(int i = 1; i <= 9; i++) {
            sb.append(i);
            helper(n, k, sb, list);
            sb.deleteCharAt(0);
        }
        
        return list.stream().mapToInt(Integer :: valueOf).toArray();
    }
    
    private void helper(int n, int k, StringBuilder sb, List<String> list) {
        if(sb.length() == n) {
            list.add(new String(sb));
            return ;
        }
        int num = sb.charAt(sb.length() - 1) - '0';
        if(num - k >= 0) {
            sb.append(num - k);
            helper(n , k, sb, list);
            sb.deleteCharAt(sb.length() - 1);
        }
        if(k != 0 && num + k <= 9) {
            sb.append(num + k);
            helper(n , k, sb, list);
            sb.deleteCharAt(sb.length() - 1);
        }
        
        
    }
}
```

###Conclustion
Runtime beat 47%
Memory beat 41%

###Related Topic
Backtracking