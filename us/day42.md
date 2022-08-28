###question
https://leetcode.com/problems/sort-the-matrix-diagonally/submissions/
###Solution
```
class Solution {
    public int[][] diagonalSort(int[][] mat) {
        Map<Integer, PriorityQueue<Integer>> map = new HashMap();
        for(int i = 0 ; i < mat.length; i++) {
            for(int j = 0; j < mat[0].length; j++) {
                map.putIfAbsent(i - j, new PriorityQueue<Integer>());
                map.get(i-j).offer(mat[i][j]);
            }
        }
        
        for(int i = 0 ; i < mat.length; i++) {
            for(int j = 0; j < mat[0].length; j++) {
                PriorityQueue<Integer> queue = map.get(i - j);
                mat[i][j] = queue.poll();
            }
        }
        return mat;
    }
}
```

###Conclustion
Runtime beat 32%
Memory beat 14%

###Related Topic
Array, Sorting