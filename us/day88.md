###question
https://leetcode.com/problems/climbing-stairs/
###Solution
```
class Solution {
    public int climbStairs(int n) {
        if(n == 1) return 1;
        if(n == 2) return 2;
        int a = 2;
        int b = 3;
        int c = 0;
        for(int i = 3; i <= n; i++) {
            c = a + b;
            a = b;
            b = c;
        }
        return a;
    }
}
```


###Conclustion
Runtime beat 100%
Memory beat 30%

###Related Topic
DP