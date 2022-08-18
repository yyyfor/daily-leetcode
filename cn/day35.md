###question
https://leetcode.cn/problems/maximum-equal-frequency/
###Solution
```
class Solution {
    public int maxEqualFreq(int[] nums) {
        int max = 1;
        int min = 1;
        int result = 1;
        Map<Integer,Set<Integer>> map = new HashMap();
        Map<Integer, Integer> map2 = new HashMap();
        for(int i = 0 ; i < nums.length; i++) {
            int num = nums[i];
            int occur = map2.getOrDefault(num, 0) + 1;
            
            map2.put(num, occur);
            if(occur == 1) {
                Set<Integer> set = map.getOrDefault(1, new HashSet<Integer>());
                set.add(num);
                map.put(1, set);
            } else {
                Set<Integer> set = map.getOrDefault(occur, new HashSet<Integer>());
                set.add(num);
                map.put(occur, set);
                
                Set<Integer> set2 = map.get(occur - 1);
                set2.remove(num);
                if(set2.isEmpty()) {
                    map.remove(occur - 1);
                } else {
                    map.put(occur - 1, set2);
                }
            }
            if(occur > max) {
                max = occur;
            }
            if(occur < min) {
                min = occur;
            }
            if(map.get(min) == null) min = occur;
            if(max == 1 || (map.keySet().size() == 1 && map.get(max).size() == 1)) {
                result = i + 1;
            }
            if(map.keySet().size() != 2) continue;
            if((min == 1 && map.get(min) != null && map.get(min).size() == 1) || (max - min == 1 && map.get(max).size() == 1)) {
                result = i + 1;
            }
            
        }
        return result;
    }   
}
```

better soludtion: use frequency map instead of set to count the frequency is enough

###Conclustion
Runtime beat 19%
Memory beat 19%

###Related Topic
Array, Hash table