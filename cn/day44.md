###question
https://leetcode.cn/problems/maximum-binary-tree-ii/comments/
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
    public TreeNode insertIntoMaxTree(TreeNode root, int val) {
        TreeNode node = new TreeNode(val);
        if(root == null) return node;
        if(root.val < val) {
            node.left = root;
            return node;
        }

        if(root.right == null) {
            root.right = node;
            return root;
        }

        if(val > root.right.val) {
            node.left = root.right;
            root.right = node;
            return root;
        }

        root.right = insertIntoMaxTree(root.right, val);
        return root;
    }
}
```

###Conclustion
Runtime beat 100%
Memory beat 35%

###Related Topic
Tree