###question
https://leetcode.com/problems/range-sum-of-bst/description/
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
    public int rangeSumBST(TreeNode root, int low, int high) {
        if(root == null) return 0;
        int left = rangeSumBST(root.left, low, high);
        int right = rangeSumBST(root.right, low, high);
        int sum = left + right;
        if(root.val >= low && root.val <= high) sum += root.val;
        return sum;
    }
}
```


###Conclustion
Runtime beat 43%
Memory beat 24%

###Related Topic
Tree