###question
https://leetcode.cn/problems/mean-of-array-after-removing-some-elements/
###Solution
```
class Solution {
    public double trimMean(int[] arr) {
        Arrays.sort(arr);
        int l = arr.length;
        double r = 0;
        for(int i = l / 20; i <= l - 1 - l / 20; i++) {
            r += arr[i];
        }
        return r / (l / 10 * 9);
    }
}
```
check max for better performance

###Conclustion
Runtime beat 99%
Memory beat 18%

###Related Topic
Array, Sorting