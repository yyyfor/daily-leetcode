###question
https://leetcode.cn/problems/my-calendar-i
###Solution
```
class MyCalendar {
    TreeSet<Node> set;
    public MyCalendar() {
        set = new TreeSet();
    }
    
    public boolean book(int start, int end) {
        Node n = new Node(start, end);
        if(set.isEmpty()) {
            set.add(n);
            return true;
        }

        Node last = set.floor(n);
        Node next = set.ceiling(n);
        if(last == null && n.next <= next.val) {
            set.add(n);
            return true;
        } 
        if(next == null && n.val >= last.next) {
            set.add(n);
            return true;
        } 

        if(last != null && next != null && n.val >= last.next && n.next <= next.val) {
            set.add(n);
            return true;
        }
        return false;
    }
}

class Node implements Comparable{
    int val;
    int next;
    public Node(int val,int next) {
        this.val = val;
        this.next = next;
    }

    @Override
    public int compareTo(Object node) {
        Node n = (Node) node;
        return this.val - n.val;
    }
}

/**
 * Your MyCalendar object will be instantiated and called as such:
 * MyCalendar obj = new MyCalendar();
 * boolean param_1 = obj.book(start,end);
 */
```

###Conclustion
Runtime beat 59%
Memory beat 58%
使用了treeset

###Related Topic
Ordered set