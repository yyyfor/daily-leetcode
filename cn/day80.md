###question
https://leetcode.cn/problems/design-linked-list/description/
###Solution
```
class MyLinkedList {

    List<Integer> list;
    public MyLinkedList() {
        list = new ArrayList();
    }
    
    public int get(int index) {
        if(list.size() <= index) return -1;
        return list.get(index);
    }
    
    public void addAtHead(int val) {
        list.add(0,val);
    }
    
    public void addAtTail(int val) {
        list.add(val);
    }
    
    public void addAtIndex(int index, int val) {
        if(list.size() < index) return ;
        list.add(index, val);
    }
    
    public void deleteAtIndex(int index) {
        if(list.size() <= index) return ;
        list.remove(index);
    }
}

/**
 * Your MyLinkedList object will be instantiated and called as such:
 * MyLinkedList obj = new MyLinkedList();
 * int param_1 = obj.get(index);
 * obj.addAtHead(val);
 * obj.addAtTail(val);
 * obj.addAtIndex(index,val);
 * obj.deleteAtIndex(index);
 */
```

Should use linked node instead of arraylist

###Conclustion
Runtime beat 100%
Memory beat 40%

###Related Topic
Linkedlist