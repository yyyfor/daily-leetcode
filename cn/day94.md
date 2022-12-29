###question
https://leetcode.com/problems/single-threaded-cpu/description/
###Solution
```
class Solution {
    public int[] getOrder(int[][] tasks) {
        int l = tasks.length;
        int [] result = new int [l];
        PriorityQueue<Node> queue1 = new PriorityQueue<Node>(
            (o1, o2) -> o1.enque - o2.enque == 0 ? o1.remain - o2.remain : o1.enque - o2.enque
        );
        PriorityQueue<Node> queue2 = new PriorityQueue<Node>(
            (o1, o2) -> o1.remain - o2.remain == 0 ? o1.index - o2.index :
            o1.remain - o2.remain 
        );
        for(int i = 0 ; i < tasks.length; i++) {
            int [] task = tasks[i];
            queue1.offer(new Node(i, task[1], task[0]));
        }
        int index = 0;
        int time = 0;
        
        while(!queue1.isEmpty()) {
            if(queue2.isEmpty()) {
                Node node = queue1.poll();
                queue2.offer(node);
                if(time == 0) time = node.enque;
            }
            System.out.println(time);
            while(!queue1.isEmpty() && queue1.peek().enque <= time) {
                queue2.offer(queue1.poll());
            }
            Node cur = queue2.poll();
            result[index++] = cur.index;
            time = Math.max(time, cur.enque);
            time = time + cur.remain;
        }
        while(!queue2.isEmpty()) {
            result[index++] = queue2.poll().index;
        }
        return result;

    }
}

class Node {
    int index;
    int remain;
    int enque;

    public Node(int index, int remain, int enque) {
        this.index = index;
        this.remain = remain;
        this.enque = enque;
    }
}
```


###Conclustion
Runtime beat 18%
Memory beat 90%

###Related Topic
PriorityQueue