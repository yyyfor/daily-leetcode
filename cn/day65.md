###question
https://leetcode.cn/problems/linked-list-components/submissions/
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
    public int numComponents(ListNode head, int[] nums) {
        Set<Integer> set = new HashSet();
        for(int num : nums) set.add(num);
        int count = 0;
        while(head != null) {
            if(set.contains(head.val)) {
                while(head != null && set.contains(head.val)) {
                    head = head.next;
                }
                count++;
            }
            if(head != null) head = head.next;
        }
        return count;
    }
}
```

###Conclustion
Runtime beat 76%
Memory beat 47%

###Related Topic
Array, Hash Table