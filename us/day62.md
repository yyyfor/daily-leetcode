###question
https://leetcode.com/problems/two-sum-iv-input-is-a-bst/
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
    Set<Integer> set = new HashSet();
    public boolean findTarget(TreeNode root, int k) {
        if(root == null) return false;
        boolean left = findTarget(root.left, k);
        boolean right = findTarget(root.right, k);
        if(left || right) return true;
        boolean exist = set.contains(k - root.val);
        set.add(root.val);
        return exist;
    }
}
```

###Conclustion
Runtime beat 81%
Memory beat 88%

###Related Topic
Tree