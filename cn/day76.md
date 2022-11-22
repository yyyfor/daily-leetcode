###question
https://leetcode.cn/problems/maximum-length-of-repeated-subarray/description/
###Solution
```
class Solution {
    public int findLength(int[] nums1, int[] nums2) {
        Map<Integer,List<Integer>> map = new HashMap();
        for(int i = 0 ; i < nums2.length; i++) {
            int num = nums2[i];
            List<Integer> list = map.getOrDefault(num, new ArrayList());
            list.add(i);
            map.put(num, list);
        }
        int max = 0;
        for(int i = 0 ; i < nums1.length; i++) {
            int num = nums1[i];
            if(map.containsKey(num)) {
                for(int n : map.get(num)) {
                    int m = i + 1;
                    int k = n + 1;
                    int count = 1;
                    max = Math.max(1, max);
                    while(m < nums1.length && k < nums2.length) {
                        if(nums1[m] == nums2[k]) {
                            count++;
                            m++;
                            k++;
                            max = Math.max(max, count);
                        } else break;
                    }
                }
            }
        }
        return max;
    }
}
```
use double loop dp for better performance
###Conclustion
Runtime beat 5%
Memory beat 84%

###Related Topic
DP