###question
https://leetcode.cn/problems/get-kth-magic-number-lcci/submissions/
###Solution
```
class Solution {
    public int getKthMagicNumber(int k) {
        int [] result = new int[k];
        result[0] = 1;
        // 定义三个 指针，分别表示 resultA、B、C 的下标
        int point3 = 0;
        int point5 = 0;
        int point7 = 0;
        for (int i = 1; i < k; i++) {
            int resultN = Math.min(Math.min(result[point3] * 3, result[point5] * 5), result[point7] * 7);
            if (resultN % 3 == 0) {
                point3++;
            }
            if (resultN % 5 == 0) {
                point5++;
            }
            if (resultN % 7 == 0) {
                point7++;
            }
            result[i] = resultN;
        }
        return result[k - 1];
    }
}
```
Use three point to record 3,5,7 value

###Conclustion
Runtime beat 100%
Memory beat 88%

###Related Topic
DP, Array