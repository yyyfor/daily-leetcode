###question
https://leetcode.com/problems/n-ary-tree-level-order-traversal/submissions/
###Solution
```
/*
// Definition for a Node.
class Node {
    public int val;
    public List<Node> children;

    public Node() {}

    public Node(int _val) {
        val = _val;
    }

    public Node(int _val, List<Node> _children) {
        val = _val;
        children = _children;
    }
};
*/

class Solution {
    public List<List<Integer>> levelOrder(Node root) {
        List<List<Integer>> result = new ArrayList();
        if(root == null) return result;
        LinkedList<Node> list = new LinkedList();
        list.add(root);
        List<Integer> l;
        while(!list.isEmpty()) {
            l = new ArrayList();
            int size = list.size();
            for(int i = 0 ; i < size; i++) {
                Node node = list.poll();
                l.add(node.val);
                if(node.children.size() != 0) {
                    list.addAll(node.children);
                }
            }
            result.add(l);
        }
        return result;
    }
}
```

###Conclustion
Runtime beat 13%
Memory beat 64%

###Related Topic
Tree, BFS