###question
https://leetcode.cn/problems/equal-sum-arrays-with-minimum-number-of-operations/submissions/387670056/
###Solution
```
class Solution {
    public int minOperations(int[] nums1, int[] nums2) {
        int m = nums1.length;
        int n = nums2.length;
        if (n > 6 * m || m > 6 * n) return -1;
        int sum1 = 0;
        int sum2 = 0;
        for (int i : nums1) sum1 += i;
        for (int i : nums2) sum2 += i;
        Arrays.sort(nums1);
        Arrays.sort(nums2);
        int res = 0;
        if (sum1 > sum2) {
            int idx1 = m - 1;
            int idx2 = 0;
            int dif = sum1 - sum2;
            while (dif > 0) {
                if (idx2 == n || idx1 >= 0 && nums1[idx1] - 1 >= 6 - nums2[idx2]) {
                    dif -= nums1[idx1] - 1;
                    --idx1;
                    ++res;
                } else {
                    dif -= 6 - nums2[idx2];
                    ++idx2;
                    ++res;
                }
            }
        } else {
            int idx1 = 0;
            int idx2 = n - 1;
            int dif = sum1 - sum2;
            while (dif < 0) {
                if (idx2 == n || idx1 < m && 6 - nums1[idx1] >= nums2[idx2] - 1) {
                    dif += 6 - nums1[idx1];
                    ++idx1;
                    ++res;
                } else {
                    dif += nums2[idx2] - 1;
                    --idx2;
                    ++res;
                }
            }
        }
        return res;
    }
}
```


###Conclustion
Runtime beat 53%
Memory beat 55%

###Related Topic
Greedy