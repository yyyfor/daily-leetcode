###question
https://leetcode.com/problems/remove-nth-node-from-end-of-list/
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
    public ListNode removeNthFromEnd(ListNode head, int n) {
        int length = 0;
        ListNode dummy = head;
        while(dummy != null) {
            dummy = dummy.next;
            length++;
        }
        if(length == n) return head.next;
        ListNode prev = null;
        int i = 0;
        dummy = head;
        while(i < length - n) {
            System.out.println(dummy.next);
            prev = dummy;
            dummy = dummy.next;
            i++;
        }
        prev.next = dummy.next;
        return head;
    }
}
```

###Conclustion
Runtime beat 6%
Memory beat 6%

use two point for one loop solution

###Related Topic
linked list 