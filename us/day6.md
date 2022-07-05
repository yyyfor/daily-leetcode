###question
https://leetcode.com/problems/longest-consecutive-sequence/
###Solution
```
class Solution {
    public int longestConsecutive(int[] nums) {
        int max = 0;
        Map<Integer,Integer> map = new HashMap();
        for(int num : nums) {
            if(!map.containsKey(num)) {
                int left = map.get(num - 1) == null ? 0 : map.get(num - 1);
                int right = map.get(num + 1) == null ? 0 : map.get(num + 1);
                int cur = left + right + 1;
                map.put(num, cur);
                map.put(num - left, cur);
                map.put(num + right, cur);
                max = Math.max(max, cur);
            } 
        }
        return max;
    }
}
```

###Conclustion
Runtime beat 69%
Memory beat 88%
考虑num如果出现过不要重复计算

###Related Topic
Array,Hash Table,Union Find