###question
https://leetcode.com/problems/reverse-linked-list-ii/
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
    public ListNode reverseBetween(ListNode head, int left, int right) {
        ListNode dummy = new ListNode(-1);
        dummy.next = head;
        ListNode newHead = dummy;
        for(int i = 1 ; i < left ; i++) {
            newHead = newHead.next;
        }
        ListNode start = newHead.next;
        ListNode then = start.next;
        for(int i = 0 ; i < right - left; i++) {
            start.next = then.next;
            then.next = newHead.next;
            newHead.next = then;
            then = start.next;
        }
        return dummy.next;
    }
}
```

###Conclustion
Runtime beat 100%
Memory beat 53%
从中间开始反转，需要标记两个node

###Related Topic
LinkedList