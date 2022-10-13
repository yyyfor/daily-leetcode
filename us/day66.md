###question
https://leetcode.com/problems/delete-node-in-a-linked-list/submissions/
###Solution
```
/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode(int x) { val = x; }
 * }
 */
class Solution {
    public void deleteNode(ListNode node) {
        node.val = node.next.val;
        node.next = node.next.next;
    }
}
```

###Conclustion
Runtime beat 100%
Memory beat 21%

###Related Topic
Linked list