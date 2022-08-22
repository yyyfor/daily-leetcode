###question
https://leetcode.cn/problems/print-binary-tree/submissions/
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
    public List<List<String>> printTree(TreeNode root) {
         // 先计算高度
        int height = -1;
        Queue<TreeNode> q = new LinkedList<>();
        q.offer(root);
        while (!q.isEmpty()) {
            int size = q.size();
            while (size-- > 0) {
                TreeNode cur = q.poll();
                if (cur.left != null) q.offer(cur.left);
                if (cur.right != null) q.offer(cur.right);
            }
            height++;
        }

        int m = height + 1, n = (1 << height + 1) - 1;
        List<List<String>> res  = new ArrayList<>();
        for (int i = 0; i < m; ++i) {
            List<String> tt = new ArrayList<>();
            for (int j = 0; j < n; ++j) {
                tt.add("");
            }
            res.add(tt);
        }
        dfs(res, root, 0, n - 1 >> 1);
        return res;
    }
    public void dfs(List<List<String>> res, TreeNode root, int x, int y) {
        if (root == null) return ;
        res.get(x).set(y, String.valueOf(root.val));
        int h = res.size() - 1;
        dfs(res, root.left, x + 1, y - (1 << h - x - 1));
        dfs(res, root.right, x + 1, y + (1 << h - x - 1));
    }
}
```

calculte height first then set value

###Conclustion
Runtime beat 90%
Memory beat 59%

###Related Topic
Tree