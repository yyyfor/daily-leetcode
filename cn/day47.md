###question
https://leetcode.cn/problems/longest-univalue-path/
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
    int max = 0;
    public int longestUnivaluePath(TreeNode root) {
        helper(root);
        return max;
    }

    private int helper(TreeNode node) {
        if(node == null) return 0;
        int left = helper(node.left);
        int right = helper(node.right);
        if(node.left != null && node.right != null && node.left.val == node.val && node.right.val == node.val) {
            max = Math.max(2 + left + right, max);
            return 1 + Math.max(left, right);
        } else if(node.left != null && node.val == node.left.val) {
            max = Math.max(1 + left, max);
            return 1 + left;
        } else if(node.right != null && node.val == node.right.val) {
            max = Math.max(1 + right, max);
            return 1 + right;
        }
        return 0;
    }
}
```

###Conclustion
Runtime beat 96%
Memory beat 30%

###Related Topic
STree