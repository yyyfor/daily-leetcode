###question
https://leetcode.cn/problems/prime-arrangements/
###Solution
```
class Solution {
    public int numPrimeArrangements(int n) {
        int count = 0;
        for(int i = 1; i <= n; i++) {
            if(isPrime(i)) count++;
        }
        System.out.println(count);
        long result = 1;
        for(int i = 2; i <= n - count; i++) {
            result *= i;
            result %= 1000000007;
        }

        for(int i = 2; i <= count; i++) {
            result *= i;
            result %= 1000000007;
        }

        return (int) result;
    }

    private boolean isPrime(int n) {
        if(n == 1) return false;
        int i = 2;
        while(i * i <= n) {
            if(n % i == 0) return false;
            i++;
        }
        return true;
    }
}
```

###Conclustion
Runtime beat 6%
Memory beat 14%
计算质数有更好的办法，可以记录已经出现的平方

###Related Topic
Math