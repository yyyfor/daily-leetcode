###question
https://leetcode.cn/problems/complete-binary-tree-inserter/comments/
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
class CBTInserter {
    List<TreeNode> l;
    int index = 0;
    public CBTInserter(TreeNode root) {
        l = new ArrayList();
        LinkedList<TreeNode> list = new LinkedList();
        list.add(root);
        while(!list.isEmpty()) {
            int size = list.size();
            for(int i = 0 ; i < size; i++) {
                TreeNode node = list.poll();
                l.add(node);
                index++;
                if(node.left != null) {
                    list.add(node.left);
                }
                if(node.right != null) {
                    list.add(node.right);
                }
            }
        }
    }
    
    public int insert(int val) {
        TreeNode node = new TreeNode(val);
        l.add(node);
        index++;
        if(l.size() == 1) return val;
        System.out.println(index);
        TreeNode parent = null;
        if(index % 2 == 1) {
            parent = l.get((index - 2) / 2);
            parent.right = node;
        } else {
            parent = l.get((index - 1) / 2);
            parent.left = node;
        }
        return parent.val;
    }
    
    public TreeNode get_root() {
        return l.get(0);
    }
}

/**
 * Your CBTInserter object will be instantiated and called as such:
 * CBTInserter obj = new CBTInserter(root);
 * int param_1 = obj.insert(val);
 * TreeNode param_2 = obj.get_root();
 */
```

###Conclustion
Runtime beat 9%
Memory beat 58%

###Related Topic
Tree