###question
https://leetcode.cn/problems/number-of-students-doing-homework-at-a-given-time/submissions/
###Solution
```
class Solution {
    public int busyStudent(int[] startTime, int[] endTime, int queryTime) {
        int count = 0;
        for(int i = 0 ; i < startTime.length; i++) {
            if(queryTime >= startTime[i] && queryTime <= endTime[i]) count++;
        }
        return count;
    }
}
```


###Conclustion
Runtime beat 100%
Memory beat 23%

###Related Topic
Array