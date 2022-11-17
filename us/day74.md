###question
https://leetcode.com/problems/rectangle-area/
###Solution
```
class Solution {
    public int computeArea(int ax1, int ay1, int ax2, int ay2, int bx1, int by1, int bx2, int by2) {
        int area1 = (ax2 - ax1) * (ay2 - ay1);
        int area2 = (bx2 - bx1) * (by2 - by1);
        int left = Math.max(ax1, bx1);
        int bottom = Math.max(ay1, by1);
        int right = Math.min(ax2, bx2);
        int top = Math.min(ay2, by2);
        int area3 = 0;
        if(top > bottom && right > left) {
            area3 = (top - bottom) * (right - left);
        }
        System.out.println(area1);
        System.out.println(area2);
        System.out.println(area3);
        return area1 + area2 - area3;
    }
}
```
###Conclustion
Runtime beat 5%
Memory beat 82%

###Related Topic
Math