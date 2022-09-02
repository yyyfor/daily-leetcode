###question
https://leetcode.com/problems/average-of-levels-in-binary-tree/submissions/
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
    public List<Double> averageOfLevels(TreeNode root) {
        List<Double> list = new ArrayList();
        LinkedList<TreeNode> queue = new LinkedList();
        queue.offer(root);
        while(!queue.isEmpty()) {
            int size = queue.size();
            double sum = 0;
            for(int i = 0 ; i < size; i++) {
                TreeNode node = queue.poll();
                sum += node.val;
                if(node.left != null) queue.offer(node.left);
                if(node.right != null) queue.offer(node.right);
            }
            list.add(sum / size);
        }
        return list;
    }
}
```

###Conclustion
Runtime beat 100%
Memory beat 93%

###Related Topic
Tree, BFS