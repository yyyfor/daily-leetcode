### question
https://leetcode.cn/problems/merge-in-between-linked-lists/description/
### Solution
```
/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode() {}
 *     ListNode(int val) { this.val = val; }
 *     ListNode(int val, ListNode next) { this.val = val; this.next = next; }
 * }
 */
class Solution {
    public ListNode mergeInBetween(ListNode list1, int a, int b, ListNode list2) {
        ListNode dummy = new ListNode(-1);
        dummy.next = list1;
        ListNode prev = null;
        int index = 0;
        while(index != a) {
            index++;
            prev = list1;
            list1 = list1.next;
        }
        while(index != b) {
            index++;
            list1 = list1.next;
        }
        list1 = list1.next;
        if(prev == null) {
            dummy.next = list2;
        } else {
            prev.next = list2;
        }
        while(list2.next != null) {
            list2 = list2.next;
        }
        
        list2.next = list1;
        return dummy.next;



    }
}
```

### Conclustion
Runtime beat 100%
Memory beat 77%

### Related Topic
LinkedList