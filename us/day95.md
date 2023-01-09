###question
https://leetcode.com/problems/binary-tree-preorder-traversal/submissions/874761597/
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
    public List<Integer> preorderTraversal(TreeNode root) {
        List<Integer> list = new ArrayList();
        helper(root, list);
        return list;
    }

    private void helper(TreeNode node, List<Integer> list) {
        if(node == null) return ;
        list.add(node.val);
        helper(node.left, list);
        helper(node.right, list);
    }
}
```


###Conclustion
Runtime beat 100%
Memory beat 58%

###Related Topic
Tree