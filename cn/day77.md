###question
https://leetcode.cn/problems/maximum-number-of-balls-in-a-box/submissions/384369894/
###Solution
```
class Solution {
    public int countBalls(int lowLimit, int highLimit) {
        int [] array = new int [highLimit + 1];
        for(int i = lowLimit; i <= highLimit; i++) {
            array[index(i)]++;
        }
        int max = 0;
        for(int i = 0 ; i <= highLimit; i++) {
            max = Math.max(array[i], max);
        }
        return max;
    }

    private int index(int num) {
        int index = 0;
        while(num != 0) {
            index += num % 10;
            num /= 10;
        }
        return index;
    }
}
```
###Conclustion
Runtime beat 53%
Memory beat 17%

###Related Topic
math, counting