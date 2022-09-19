###question
https://leetcode.cn/problems/sort-array-by-increasing-frequency/
###Solution
```
class Solution {
    public int[] frequencySort(int[] nums) {
        Map<Integer,Integer> map = new HashMap();
        for(int num: nums) {
            map.put(num, map.getOrDefault(num, 0) + 1);
        }
        List<Node> list = new ArrayList();
        for(Map.Entry<Integer,Integer> entry: map.entrySet()) {
            int val = entry.getKey();
            int f = entry.getValue();
            Node node = new Node(val, f);
            list.add(node);
        }
        int [] array = new int [nums.length];
        int index = 0;
        Collections.sort(list, (o1, o2) -> o1.f == o2.f ? o2.val - o1.val: o1.f - o2.f);
        for(int i = 0 ; i < list.size(); i++) {
            Node node = list.get(i);
            for(int j = 0 ; j < node.f; j++) {
                array[index++] = node.val;
            }
        }
        return array;
    }
}

class Node {
    int val;
    int f;
    
    public Node(int val, int f) {
        this.val = val;
        this.f = f;
    }
}
```

###Conclustion
Runtime beat 63%
Memory beat 99%

###Related Topic
Array, Hash Table