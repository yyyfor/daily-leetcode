###question
https://leetcode.com/problems/validate-binary-search-tree/
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
    Integer prev = null;
    public boolean isValidBST(TreeNode root) {
        if(root == null) return true;
        boolean left = isValidBST(root.left);
        if(prev != null && root.val <= prev) return false;
        prev = root.val;
        boolean right = isValidBST(root.right);
        return left && right;
        
    }
}
```

###Conclustion
Runtime beat 100%
Memory beat 87%

###Related Topic
Tree, BST