###question
https://leetcode.cn/problems/advantage-shuffle/
###Solution
```
class Solution {
    public int[] advantageCount(int[] nums1, int[] nums2) {
        TreeMap<Integer,Integer> set = new TreeMap();
        int [] r = new int [nums1.length];
        int index = 0;
        for(int num : nums1) {
            set.put(num, set.getOrDefault(num , 0) + 1);
        }
        for(int i = 0 ; i < nums2.length; i++) {
            int num = nums2[i];
            Integer n = set.higherKey(num);
            Map.Entry<Integer,Integer> entry = null;
            if(n == null) {
                entry = set.firstEntry();
            } else {
                entry = set.higherEntry(num);
            }
            r[index++] = entry.getKey();
            if(entry.getValue() == 1) set.remove(entry.getKey());
            else set.put(entry.getKey(), set.get(entry.getKey()) - 1);
        }
        return r;
    }
}
```

###Conclustion
Runtime beat 5%
Memory beat 94%

###Related Topic
Greedy, Array