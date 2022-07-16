###question
https://leetcode.cn/problems/qIsx9U/
###Solution
```
class MovingAverage {
    LinkedList<Integer> list;
    int sum;
    int size;

    /** Initialize your data structure here. */
    public MovingAverage(int size) {
        list = new LinkedList();    
        sum = 0;
        this.size = size;
    }
    
    public double next(int val) {
        sum += val;
        list.add(val);
        if(list.size() > size) {
            sum -= list.pollFirst();
        }
        return (double)sum / list.size();
    }
}
```

###Conclustion
Runtime beat 97%
Memory beat 17%

###Related Topic
Array