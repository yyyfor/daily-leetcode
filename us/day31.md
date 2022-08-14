###question
https://leetcode.com/problems/smallest-string-starting-from-leaf/submissions/
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
    public String smallestFromLeaf(TreeNode root) {
    return dfs(root, "");
}

public String dfs(TreeNode node, String suffix) {
    if(null == node) {
        return suffix;
    }
    suffix = "" + (char)('a' + node.val) + suffix;
    if(null == node.left && null == node.right) {
        return suffix;
    }
    if(null == node.left || null == node.right) {
        return (null == node.left)? dfs(node.right, suffix) :dfs(node.left, suffix);
    }
    
    String left = dfs(node.left, suffix);
    String right = dfs(node.right, suffix);
    
    return left.compareTo(right) <= 0? left: right;
}
}
```

###Conclustion
Runtime beat 34%
Memory beat 47%

###Related Topic
Tree, DFS