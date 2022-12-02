###question
https://leetcode.cn/problems/minimum-number-of-operations-to-move-all-balls-to-each-box/description/
###Solution
```
class Solution {
    public int[] minOperations(String boxes) {
        int l = boxes.length();
        int [] result = new int [l];
        int total = 0;
        int sum = 0;
        for(int i = 1 ; i < l; i++) {
            if(boxes.charAt(i) == '1') {
                total++;
                sum += i;
            }
        }
        int cur = boxes.charAt(0) == '0' ? 0 : 1;
        result[0] = sum;
        for(int i = 1; i < l; i++) {
            
            sum = sum - total + cur;
            if(boxes.charAt(i) == '1') {
                cur++;
                total--;
            }
            result[i] = sum;
        }
        return result;
    }
}
```


###Conclustion
Runtime beat 98%
Memory beat 89%

###Related Topic
Array, String