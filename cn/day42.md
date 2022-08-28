###question
https://leetcode.cn/problems/preimage-size-of-factorial-zeroes-function/submissions/
###Solution
```
class Solution {
    public int preimageSizeFZF(int k) {
        long start = 0;
        long end = (long)Math.pow(10, 10) + 1;
        while(start < end) {
            long mid = start + (end - start) / 2;
            int n = getFive(mid);
            if(n == k) return 5;
            if(n > k) {
                end = mid - 1;
            } else {
                start = mid + 1;
            }
        }
        return 0;
    }

    private int getFive(long n) {
        int sum = 0;
        long start = 5;
        while(start < n) {
            sum += n / start;
            start *= 5;
        }
        return sum;
    }
}
```

###Conclustion
Runtime beat 100%
Memory beat 65%

###Related Topic
Math, Binary search