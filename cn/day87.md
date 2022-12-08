###question
https://leetcode.cn/problems/determine-color-of-a-chessboard-square/description/
###Solution
```
class Solution {
    public boolean squareIsWhite(String coordinates) {
        char num = coordinates.charAt(0);
        char al = coordinates.charAt(1);
        int n1 = num - '1';
        int n2 = al - 'a';
        return Math.abs(n1 - n2) % 2 == 1;
    }
}
```


###Conclustion
Runtime beat 100%
Memory beat 73%

###Related Topic
Math