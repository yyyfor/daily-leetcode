###question
https://leetcode.cn/problems/final-value-of-variable-after-performing-operations/description/
###Solution
```
class Solution {
    public int finalValueAfterOperations(String[] operations) {
        int count = 0;
        for(String s: operations) {
            count += cal(s);
        }
        return count;
    }

    private int cal(String s) {
        if(s.indexOf("+") != -1) return 1;
        else return -1;
    }
}
```


###Conclustion
Runtime beat 100%
Memory beat 12%

###Related Topic
String