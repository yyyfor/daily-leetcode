###question
https://leetcode.com/problems/fibonacci-number/
###Solution
```
class Solution {
    public int fib(int n) {
        if(n == 0) return 0;
        int a = 1;
        int b = 0;
        int c = 0;
        for(int i = 2; i <= n; i++) {
            c = a + b;
            b = a;
            a = c;
        }
        return a;
    }
}
```

###Conclustion
Runtime beat 100%
Memory beat 13%
迭代比递归快

###Related Topic
math,dp,memoization