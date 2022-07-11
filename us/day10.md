###question
https://leetcode.com/problems/binary-tree-right-side-view/
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
    public List<Integer> rightSideView(TreeNode root) {
        LinkedList<TreeNode> list = new LinkedList();
        List<Integer> r = new ArrayList();
        if(root == null) return r;
        list.add(root);
        while(!list.isEmpty()) {
            int size = list.size();
            for(int i = 0 ; i < size; i++) {
                TreeNode node = list.poll();
                if(i == size - 1) r.add(node.val);
                if(node.left != null) list.add(node.left);
                if(node.right != null) list.add(node.right);
            }
        }
        return r;
    }
}
```

###Conclustion
Runtime beat 95%
Memory beat 23%
注意root为空情况

###Related Topic
tree