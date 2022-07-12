###question
https://leetcode.cn/problems/cells-with-odd-values-in-a-matrix/
###Solution
```
class Solution {
    public int oddCells(int m, int n, int[][] indices) {
        int [][] r = new int[m][n];
        for(int [] indice : indices) {
            int row = indice[0];
            int column = indice[1];
            for(int i = 0 ; i < m; i++) {
                r[i][column]++;
            }
            for(int i = 0 ; i < n; i++) {
                r[row][i]++;
            }
        }
        int count = 0;
        for(int i = 0 ; i < m ; i++) {
            for(int j = 0 ; j < n; j++) {
                if(r[i][j] % 2 == 1) count++;
            }
        }
        return count;
    }
}
```

###Conclustion
Runtime beat 55%
Memory beat 65%

###Related Topic
Array, math