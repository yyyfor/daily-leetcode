###question
https://leetcode.com/problems/roman-to-integer/submissions/
###Solution
```
class Solution {
    public int romanToInt(String s) {
        int result = 0;
        for(int i = 0 ; i < s.length(); i++) {
            char ch = s.charAt(i);
            if(ch == 'I') result += 1;
            if(ch == 'V') {
                result += 5;
                if(i != 0 && s.charAt(i - 1) == 'I') result-=2;
            }
            if(ch == 'X') {
                result += 10;
                if(i != 0 && s.charAt(i - 1) == 'I') result-=2;
            }
            if(ch == 'L') {
                result += 50;
                if(i != 0 && s.charAt(i - 1) == 'X') result-=20;
            }
            if(ch == 'C') {
                result += 100;
                if(i != 0 && s.charAt(i - 1) == 'X') result-=20;
            }
            if(ch == 'D') {
                result += 500;
                if(i != 0 && s.charAt(i - 1) == 'C') result-=200;
            }
            if(ch == 'M') {
                result += 1000;
                if(i != 0 && s.charAt(i - 1) == 'C') result-=200;
            }
        }
        return result;
    }
}
```

###Conclustion
Runtime beat 94%
Memory beat 82%

###Related Topic
Hash table, Math