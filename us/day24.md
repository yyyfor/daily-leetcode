###question
https://leetcode.com/problems/my-calendar-i/submissions/
###Solution
```
class MyCalendar {
    
    TreeSet<int []> set;

    public MyCalendar() {
        set = new TreeSet<>( (o1, o2) -> 
                                 o1[0] == o2[0] ? o1[1] - o2[1]: o1[0] - o2[0]);
    }
    
    public boolean book(int start, int end) {
        if(set.isEmpty()) {
            set.add(new int [] {start, end});
            return true;
        }
        int [] array = new int [] {start, end};
        int [] last = set.lower(array);
        int [] next = set.ceiling(array);
        if(last != null && last[1] > start || (next != null) && next[0] < end) return false;
        set.add(array);
        return true;
    }
}

/**
 * Your MyCalendar object will be instantiated and called as such:
 * MyCalendar obj = new MyCalendar();
 * boolean param_1 = obj.book(start,end);
 */
```

###Conclustion
Runtime beat 60%
Memory beat 10%

###Related Topic
Design, Ordered set