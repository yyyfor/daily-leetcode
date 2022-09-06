###question
https://leetcode.com/problems/binary-tree-pruning/submissions/
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
    public TreeNode pruneTree(TreeNode root) {
        delete(root);
        if(root.val == 0 && root.left == null && root.right == null) return null;
        return root;
    }
    
    private boolean delete(TreeNode node) {
        if(node == null) return true;
        boolean left = delete(node.left);
        boolean right = delete(node.right);
        if(left) {
            node.left = null;
        }
        if(right) {
            node.right = null;
        }
        if(left && right && node.val == 0) return true;
        return false;
    }
}
```

###Conclustion
Runtime beat 100%
Memory beat 26%

###Related Topic
Tree