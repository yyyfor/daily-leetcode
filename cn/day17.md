###question
https://leetcode.cn/problems/binary-tree-pruning
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
        int num = helper(root);
        return num == 0 ? null : root;
    }

    private int helper(TreeNode root) {
        if(root == null) return 0;
        int left = helper(root.left);
        int right = helper(root.right);
        if(left == 0) root.left = null;
        if(right == 0) root.right = null;
        return left + right + root.val;
    }
}
```

###Conclustion
Runtime beat 100%
Memory beat 80%
注意根也需要剪掉

###Related Topic
Tree