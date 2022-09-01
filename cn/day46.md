###question
https://leetcode.cn/problems/final-prices-with-a-special-discount-in-a-shop/
###Solution
```
class Solution {
    public int[] finalPrices(int[] prices) {
        for(int i = 0 ; i < prices.length - 1; i++) {
            for(int j = i + 1; j < prices.length; j++) {
                if(prices[i] >= prices[j]) {
                    prices[i] -= prices[j];
                    break;
                }
            }
        }
        return prices;
    }
}
```

###Conclustion
Runtime beat 98%
Memory beat 70%

###Related Topic
Stack, Array