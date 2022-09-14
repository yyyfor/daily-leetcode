###question
https://leetcode.com/problems/pseudo-palindromic-paths-in-a-binary-tree/submissions/
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
    int count = 0;
    public int pseudoPalindromicPaths (TreeNode root) {
        helper(new HashSet<Integer>(), root);
        return count;
    }
    
    private void helper(Set<Integer> list, TreeNode node) {
        if(node == null) {
            return ;
        }
        if(list.contains(node.val)) list.remove(node.val);
        else list.add(node.val);
        if(node.left == null && node. right == null) {
            if(list.size() <= 1) count++;
            if(list.contains(node.val)) list.remove(node.val);
            else list.add(node.val);
            return ;
        }
        helper(list, node.left);
        helper(list, node.right);
        if(list.contains(node.val)) list.remove(node.val);
        else list.add(node.val);
    }
}
```
check max for better performance

###Conclustion
Runtime beat 25%
Memory beat 21%

use xor for better performance

###Related Topic
Tree, Bit manipulation