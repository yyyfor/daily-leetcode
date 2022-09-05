###question
https://leetcode.cn/problems/find-duplicate-subtrees/submissions/
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
    List<TreeNode> res = new ArrayList<>();
    public List<TreeNode> findDuplicateSubtrees(TreeNode root) {
        Map<String, Integer> map = new HashMap<>();
        dfs(root, map);
        return res;
    }
    private String dfs(TreeNode root, Map<String, Integer> map){
        if(root == null) return "#";
        String str = "";
        str = (root.val)+" "+ dfs(root.left, map)+ " " + dfs(root.right, map);
        if(map.getOrDefault(str, 0) == 1) res.add(root);
        map.put(str, map.getOrDefault(str, 0)+1);
        return str;
    }
}
```

###Conclustion
Runtime beat 80%
Memory beat 64%

use map to record visited node

###Related Topic
Tree, DFS