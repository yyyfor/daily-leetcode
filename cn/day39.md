###question
https://leetcode.cn/problems/make-two-arrays-equal-by-reversing-sub-arrays/comments/
###Solution
```
class Solution {
    public boolean canBeEqual(int[] target, int[] arr) {
        Map<Integer,Integer> map = new HashMap();
        for(int num: target) {
            map.put(num, map.getOrDefault(num, 0) + 1);
        }
        for(int num: arr) {
            if(!map.containsKey(num)) return false;
            map.put(num, map.get(num) - 1);
            if(map.get(num) < 0) return false;
        }
        return true;
    }
}
```

###Conclustion
Runtime beat 12%
Memory beat 5%

###Related Topic
Array