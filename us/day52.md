###question
https://leetcode.com/problems/construct-string-from-binary-tree/
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
    public String tree2str(TreeNode t) {
        if(t == null) return null;
        String s = String.valueOf(t.val);
        String left = tree2str(t.left);
        String right = tree2str(t.right);
        if(left != null) {
            s += "(" + left + ")";
            if(right != null) {
                s += "(" + right + ")";
            }
        } else if(right != null) {
            s += "(" + ")";
            s += "(" + right + ")";
        }
        return s;
    }
}
```

###Conclustion
Runtime beat 48%
Memory beat 43%

###Related Topic
Tree, String