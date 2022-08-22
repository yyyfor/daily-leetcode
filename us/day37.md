###question
https://leetcode.com/problems/power-of-four/submissions/
###Solution
```
class Solution {
    public boolean isPowerOfFour(int n) {
        if(n == 0) return false;
        while(n != 0 && n != 1) {
            if(n % 4 != 0) return false;
            n /= 4;
        }
        return n == 1;
    }
}
```


###Conclustion
Runtime beat 100%
Memory beat 96%

###Related Topic
Math