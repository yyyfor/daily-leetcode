###question
https://leetcode.com/problems/count-good-nodes-in-binary-tree/submissions/
###Solution
```
/**
 * Definition for a binary tree node.
 * public class TreeNode {
 *     int val;
 *     TreeNode left;
 *     TreeNode right;
 *     TreeNode() {}
 *     TreeNode(int val) { this.val = val; }
 *     TreeNode(int val, TreeNode left, TreeNode right) {
 *         this.val = val;
 *         this.left = left;
 *         this.right = right;
 *     }
 * }
 */
class Solution {
    int count = 0;
    public int goodNodes(TreeNode root) {
        helper(root, Integer.MIN_VALUE);
        return count;
    }
    
    private void helper(TreeNode node, int max) {
        if(node == null) return ;
        if(node.val >= max) {
            count++;
            max = node.val;
        }
        
        helper(node.left, max);
        helper(node.right, max);
    }
}
```

###Conclustion
Runtime beat 100%
Memory beat 89%

###Related Topic
Tree