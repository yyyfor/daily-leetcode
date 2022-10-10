###question
https://leetcode.com/problems/break-a-palindrome/
###Solution
```
class Solution {
    public String breakPalindrome(String palindrome) {
        char [] chs = palindrome.toCharArray();
        for(int i = 0 ; i < chs.length / 2; i++) {
            if(chs[i] != 'a') {
                chs[i] = 'a';
                return String.valueOf(chs);
            }
        }
        chs[chs.length - 1] = 'b';
        return chs.length < 2 ? "" : String.valueOf(chs);
    }
}
```

###Conclustion
Runtime beat 100%
Memory beat 31%

###Related Topic
String, Greedy