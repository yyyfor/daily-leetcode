###question
https://leetcode.com/problems/maximum-bags-with-full-capacity-of-rocks/description/
###Solution
```
class Solution {
    public int maximumBags(int[] capacity, int[] rocks, int additionalRocks) {
        int count = 0;
        PriorityQueue<Integer> queue = new PriorityQueue();
        for(int i = 0 ; i < capacity.length; i++) {
            int diff = capacity[i] - rocks[i];
            if(diff == 0) count++;
            else {
                queue.offer(diff);
            }
        }
        while(additionalRocks > 0 && !queue.isEmpty()) {
            int diff = queue.poll();
            if(additionalRocks >= diff) {
                additionalRocks -= diff;
                count++;
            } else break;
        }
        return count;
    }
}
```


###Conclustion
Runtime beat 23%
Memory beat 93%

###Related Topic
Greedy