###question
https://leetcode.com/problems/reduce-array-size-to-the-half/submissions/
###Solution
```
class Solution {
    public int minSetSize(int[] arr) {
        int sum = arr.length;
        Map<Integer,Integer> map = new HashMap();
        for(int num: arr) {
            map.put(num, map.getOrDefault(num, 0) + 1);
        }
        
        PriorityQueue<Node> queue = new PriorityQueue<Node>( 
        (o1, o2) -> o2.count - o1.count);
        for(Map.Entry<Integer,Integer> entry: map.entrySet()) {
            Node node = new Node(entry.getKey(), entry.getValue());
            queue.offer(node);
        }
        int now = sum;
        int result = 1;
        while(!queue.isEmpty()) {
            now -= queue.poll().count;
            if(now <= sum / 2) {
                return result;
            }
            result++;
        }
        return result;
        
    }
}

class Node {
    int val;
    int count;
    
    public Node(int val, int count) {
        this.val = val;
        this.count = count;
    }
}
```

###Conclustion
Runtime beat 84%
Memory beat 88%

###Related Topic
Array, Hash table, Sorting