###question
https://leetcode.cn/problems/find-nearest-point-that-has-the-same-x-or-y-coordinate/description/
###Solution
```
class Solution {
    public int nearestValidPoint(int x, int y, int[][] points) {
        int min = Integer.MAX_VALUE;
        int num = -1;
        for(int i = 0 ; i < points.length; i++) {
            int [] point = points[i];
            int x1 = point[0];
            int y1 = point[1];
            if(x != x1 && (y1 != y)) continue;
            int tmp = Math.abs(x - x1) + Math.abs(y - y1);
            if(tmp < min) {
                min = tmp;
                num = i;
            }
        }
        return num;
    }
}
```


###Conclustion
Runtime beat 34%
Memory beat 74%

###Related Topic
Array