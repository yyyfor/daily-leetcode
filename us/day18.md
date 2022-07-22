###question
https://leetcode.com/problems/partition-list
###Solution
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
    public ListNode partition(ListNode head, int x) {
        ListNode dummy1 = new ListNode(-1000);
        ListNode dummy2 = new ListNode(-1000);
        ListNode head1 = dummy1;
        ListNode head2 = dummy2;
        while(head != null) {
            if(head.val < x) {
                dummy1.next = new ListNode(head.val);
                dummy1 = dummy1.next;
            } else {
                dummy2.next = new ListNode(head.val);
                dummy2 = dummy2.next;
            }
            head = head.next;
        }
        if(dummy2.val != -1000) {
            dummy1.next = head2.next;
        }
        return head1.next;
    }
}
```

###Conclustion
Runtime beat 69%
Memory beat 23%

###Related Topic
Linkedlist, two point