###question
https://leetcode.cn/problems/deepest-leaves-sum/submissions/
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
    public int deepestLeavesSum(TreeNode root) {
        int sum = 0;
        LinkedList<TreeNode> list = new LinkedList();
        list.offer(root);
        while(!list.isEmpty()) {
            sum = 0;
            int size = list.size();
            for(int i = 0 ; i < size; i++) {
                TreeNode node = list.poll();
                sum += node.val;
                if(node.left != null) {
                    list.offer(node.left);
                }
                if(node.right != null) {
                    list.offer(node.right);
                }
            }
        }
        return sum;
    }
}
```

###Conclustion
Runtime beat 53%
Memory beat 92%

###Related Topic
Tree, BFS