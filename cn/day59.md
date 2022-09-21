###question
https://leetcode.cn/problems/partition-to-k-equal-sum-subsets/
###Solution
```
class Solution {
    public int computeArea(int ax1, int ay1, int ax2, int ay2, int bx1, int by1, int bx2, int by2) {
        int sum = (ax2 - ax1) * (ay2 - ay1);
        int sum2 = (bx2 - bx1) * (by2 - by1);
        if(ax2 <= bx1 || bx2 <= ax1 || ay2 <= by1 || by2 <= ay1) return sum + sum2;
        int x = Math.min(ax2, bx2) - Math.max(ax1, bx1);
        int y = Math.min(ay2, by2) - Math.max(ay1, by1);
        return sum - x * y + sum2;
    }
}
```

###Conclustion
Runtime beat 100%
Memory beat 88%

###Related Topic
Math