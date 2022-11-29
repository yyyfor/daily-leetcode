###question
https://leetcode.cn/problems/minimum-changes-to-make-alternating-binary-string/discussion/
###Solution
```
class Solution {
    public int minOperations(String s) {
        StringBuilder sb = new StringBuilder();
        for(int i = 0 ; i < s.length(); i++) {
            if(i % 2 == 0) {
                sb.append("0");
            } else {
                sb.append("1");
            }
        }
        String s2 = sb.toString();
        int n1 = 0;
        int n2 = 0;
        for(int i = 0 ; i < s.length(); i++) {
            if(s2.charAt(i) == s.charAt(i)) {
                n2++;
            } else n1++;
        }
        return Math.min(n1, n2);
    }
}
```

use one loop

###Conclustion
Runtime beat 13%
Memory beat 8%

###Related Topic
String