###question
https://leetcode.cn/problems/find-k-closest-elements/comments/
###Solution
```
class Solution {
    public List<Integer> findClosestElements(int[] arr, int k, int x) {
        PriorityQueue<Integer> queue1 = new PriorityQueue(Collections.reverseOrder());
        PriorityQueue<Integer> queue2 = new PriorityQueue();
        for(int num: arr) {
            if(num <= x) queue1.offer(num);
            else queue2.offer(num);
        }
        List<Integer> list = new ArrayList();
        while(!queue1.isEmpty() && !queue2.isEmpty()) {
            System.out.println(queue1.peek());
            System.out.println(queue2.peek());
            if(x - queue1.peek() > queue2.peek() - x) {
                list.add(queue2.poll());
            } else {
                list.add(queue1.poll());
            }
            if(list.size() == k) {
                Collections.sort(list);
                return list;
            }
        }
        while(list.size() < k) {
            if(!queue1.isEmpty()) {
                list.add(queue1.poll());
            }
            if(!queue2.isEmpty()) {
                list.add(queue2.poll());
            }
            if(list.size() == k) {
                Collections.sort(list);
                return list;
            }
        }
        Collections.sort(list);
        return list;
    }
}
```

better solution could use two point from two side

###Conclustion
Runtime beat 5%
Memory beat 100%

###Related Topic
Array, Sorting, Heap