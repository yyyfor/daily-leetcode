###question
https://leetcode.cn/problems/generate-a-string-with-characters-that-have-odd-counts/
###Solution
```
class Solution {
    public String generateTheString(int n) {
        StringBuilder sb = new StringBuilder();
        for(int i = 0 ; i < n - 1; i++) {
            sb.append("a");
        }
        if(n % 2 == 1) {
            sb.append("a");
        } else {
            sb.append("b");
        }
        return sb.toString();
    }
}
```

###Conclustion
Runtime beat 69%
Memory beat 20%

###Related Topic
String