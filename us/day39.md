###question
https://leetcode.com/problems/power-of-three/
###Solution
```
class Solution {
    public boolean isPowerOfThree(int n) {
        if(n == 0) return false;
        while(n >= 2) {
            if(n % 3 != 0) return false;
            n /= 3;
        }
        return n == 1;
    }
}
```

###Conclustion
Runtime beat 14%
Memory beat 62%

###Related Topic
Math