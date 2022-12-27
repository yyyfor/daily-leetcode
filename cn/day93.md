###question
https://leetcode.cn/problems/minimum-moves-to-convert-string/description/
###Solution
```
class Solution {
    public int minimumMoves(String s) {
        int count = 0;
        for(int i = 0 ; i < s.length(); i++) {
            char ch = s.charAt(i);
            if(ch == 'X') {
                count++;
                i = i + 2;
            }
        }
        return count;
    }
}
```


###Conclustion
Runtime beat 64%
Memory beat 67%

###Related Topic
String, Greedy