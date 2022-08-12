###question
https://leetcode.cn/problems/group-the-people-given-the-group-size-they-belong-to/
###Solution
```
class Solution {
    public List<List<Integer>> groupThePeople(int[] groupSizes) {
        Map<Integer,List<Integer>> map = new HashMap();
        for(int i = 0 ; i < groupSizes.length; i++) {
            int size = groupSizes[i];
            List<Integer> list = map.getOrDefault(size, new ArrayList());
            list.add(i);
            map.put(size, list);
        }
        List<List<Integer>> result = new ArrayList();
        for(Map.Entry<Integer, List<Integer>> entry : map.entrySet()) {
            int key = entry.getKey();
            List<Integer> list = entry.getValue();
            List<Integer> l = new ArrayList();
            for(int i = 0 ; i < list.size(); i++) {
                l.add(list.get(i));
                if(l.size() == key) {
                    result.add(l);
                    l = new ArrayList();
                }
            }
        }
        return result;
    }
}
```

###Conclustion
Runtime beat 8%
Memory beat 93%

###Related Topic
Array, Hash table