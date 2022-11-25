###question
https://leetcode.com/problems/find-largest-value-in-each-tree-row/submissions/
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
    public List<Integer> largestValues(TreeNode root) {
        List<Integer> list = new ArrayList();
        if(root == null) return list;
        LinkedList<TreeNode> queue = new LinkedList();
        queue.add(root);
        while(!queue.isEmpty()) {
            int size = queue.size();
            int max = Integer.MIN_VALUE;
            for(int i = 0 ; i < size; i++) {
                TreeNode node = queue.poll();
                max = Math.max(max, node.val);
                if(node.left != null) queue.offer(node.left);
                if(node.right != null) queue.offer(node.right);
            }
            list.add(max);
        }
        return list;
    }
}
```
###Conclustion
Runtime beat 100%
Memory beat 87%

###Related Topic
BFS