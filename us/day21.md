###question
https://leetcode.com/problems/flatten-binary-tree-to-linked-list/
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
    List<TreeNode> list = new ArrayList();
    public void flatten(TreeNode root) {
        if(root == null) return ;
        helper(root);
        TreeNode newHead = root;
        for(int i = 1; i < list.size(); i++) {
            TreeNode node = list.get(i);
            root.right = node;
            root.left = null;
            root = root.right;
        }
        root = newHead.right;
    }
    
    private void helper(TreeNode root) {
        if(root == null) return ;
        list.add(root);
        helper(root.left);
        helper(root.right);
    }
}
```

###Conclustion
Runtime beat 16%
Memory beat 23%

###Related Topic
LinkedList, Tree