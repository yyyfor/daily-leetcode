###question
https://leetcode.com/problems/insert-interval/solutions/
###Solution
```
class Solution {
    public int[][] insert(int[][] intervals, int[] newInterval) {
        if(newInterval == null || newInterval.length == 0) return intervals;
        List<int []> list = new ArrayList();
        int start = newInterval[0];
        int end = newInterval[1];
        boolean added = false;
        for(int [] interval : intervals) {
            if(interval[1] < start) {
                list.add(interval);
                continue;
            }
            if(interval[0] > end) {
                if(!added) {
                    added = true;
                    list.add(new int [] {start, end});
                }
                list.add(interval);
                continue;
            }
            start = Math.min(start, interval[0]);
            end = Math.max(end, interval[1]);
        }
        if(!added) {
            list.add(new int [] {start, end});
        }
        int index = 0;
        int[][] result = new int [list.size()][2];
        for(int [] array: list) {
            result[index++] = array;
        }
        return result;
    }
}
```


###Conclustion
Runtime beat 99%
Memory beat 58%

###Related Topic
Array