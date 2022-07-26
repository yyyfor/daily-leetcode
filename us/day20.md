###question
https://leetcode.com/problems/lowest-common-ancestor-of-a-binary-tree/
###Solution
```
/**
 * Definition for a binary tree node.
 * public class TreeNode {
 *     int val;
 *     TreeNode left;
 *     TreeNode right;
 *     TreeNode(int x) { val = x; }
 * }
 */
class Solution {
    public TreeNode lowestCommonAncestor(TreeNode root, TreeNode p, TreeNode q) {
        if(root == null) return null;
        TreeNode left = lowestCommonAncestor(root.left, p, q);
        TreeNode right = lowestCommonAncestor(root.right, p, q);
        if(left != null && right != null) return root;
        if(root.val == p.val || root.val == q.val) return root;
        return left == null? right : left;
    }
}
```

###Conclustion
Runtime beat 66%
Memory beat 45%

###Related Topic
Tree, DFS