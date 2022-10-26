###question
https://leetcode.cn/problems/bu-yong-jia-jian-cheng-chu-zuo-jia-fa-lcof/submissions/
###Solution
```
class Solution {
    public int add(int a, int b) {
        int sum = a ^ b;
        int c = (a & b) << 1;
        while(c != 0) {
            a = sum;
            b = c;
            sum = a ^ b;
            c = (a & b) << 1;
        }
        return sum;
    }
}
```
consider ^ and <<

###Conclustion
Runtime beat 100%
Memory beat 6%

###Related Topic
Bit manipulation