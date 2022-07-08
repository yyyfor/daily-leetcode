###question
https://leetcode.cn/problems/minimum-cost-to-move-chips-to-the-same-position
###Solution
```
class Solution {
    public int minCostToMoveChips(int[] position) {
        int odd = 0;
        int even = 0;
        for(int num : position) {
            if(num % 2 == 0) even++;
            else odd++;
        }
        return Math.min(even, odd);
    }
}
```

###Conclustion
Runtime beat 100%
Memory beat 39%
计算奇偶的个数算最小值

###Related Topic
array,math