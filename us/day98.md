###question
https://leetcode.com/problems/data-stream-as-disjoint-intervals/submissions/886900347/
###Solution
```
class SummaryRanges {
    Set<Integer> set;
    /** Initialize your data structure here. */
    public SummaryRanges() {
        set = new TreeSet();
    }
    
    public void addNum(int val) {
        set.add(val);
    }
    
    public int[][] getIntervals() {
        if(set.isEmpty()) return new int [0][0];
        List<int []> list = new ArrayList();
        int left = -1;
        int right = -1;
        for(int num : set) {
            if(left < 0) {
                left = num;
                right = num;
            } else if(num == right + 1) {
                right = num;
            } else {
                list.add(new int [] {left, right});
                left = num;
                right = num;
            }
        }
        list.add(new int [] {left, right});
        return list.toArray(new int [0][]);
    }
}

/**
 * Your SummaryRanges object will be instantiated and called as such:
 * SummaryRanges obj = new SummaryRanges();
 * obj.addNum(val);
 * int[][] param_2 = obj.getIntervals();
 */
```


###Conclustion
Runtime beat 9%
Memory beat 5%

###Related Topic
Ordered set