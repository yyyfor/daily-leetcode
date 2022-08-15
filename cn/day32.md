###question
https://leetcode.cn/problems/design-circular-deque/
###Solution
```
class MyCircularDeque {
    List<Integer> list;
    int size;
    public MyCircularDeque(int k) {
        list = new ArrayList();
        size = k;
    }
    
    public boolean insertFront(int value) {
        if(list.size() == size) return false;
        list.add(0, value);
        return true;
    }
    
    public boolean insertLast(int value) {
        if(list.size() == size) return false;
        list.add(value);
        return true;
    }
    
    public boolean deleteFront() {
        if(list.isEmpty()) return false;
        list.remove(0);
        return true;
    }
    
    public boolean deleteLast() {
        if(list.isEmpty()) return false;
        list.remove(list.size() - 1);
        return true;
    }
    
    public int getFront() {
        if(list.isEmpty()) return -1;
        return list.get(0);
    }
    
    public int getRear() {
        if(list.isEmpty()) return -1;
        return list.get(list.size() - 1);
    }
    
    public boolean isEmpty() {
        return list.isEmpty();
    }
    
    public boolean isFull() {
        return list.size() == size;
    }
}

/**
 * Your MyCircularDeque object will be instantiated and called as such:
 * MyCircularDeque obj = new MyCircularDeque(k);
 * boolean param_1 = obj.insertFront(value);
 * boolean param_2 = obj.insertLast(value);
 * boolean param_3 = obj.deleteFront();
 * boolean param_4 = obj.deleteLast();
 * int param_5 = obj.getFront();
 * int param_6 = obj.getRear();
 * boolean param_7 = obj.isEmpty();
 * boolean param_8 = obj.isFull();
 */
```

###Conclustion
Runtime beat 20%
Memory beat 93%

use array have better performance

###Related Topic
Array, Queue