###question
https://leetcode.com/problems/binary-tree-level-order-traversal/
###Solution
```
class Solution {
    public List<List<Integer>> levelOrder(TreeNode root) {
        
        LinkedList<TreeNode> list = new LinkedList();
        
        List<Integer> l;
        List r = new ArrayList();
        if(root == null) return r;
        
        list.offer(root);
        while(!list.isEmpty()) {
            l = new ArrayList();
            int size = list.size();
            for(int i = 0 ; i < size; i++) {
                TreeNode node = list.poll();
                l.add(node.val);
                if(node.left != null) list.offer(node.left);
                if(node.right != null) list.offer(node.right);
            }
            r.add(l);
        }
        return r;
    }
}
```

###Conclustion
Runtime beat 100%
Memory beat 98%

###Related Topic
Tree, bfs