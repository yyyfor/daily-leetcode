###question
https://leetcode.com/problems/toeplitz-matrix/submissions/
###Solution
```
class Solution {
    public boolean isToeplitzMatrix(int[][] matrix) {
        int m = matrix.length;
        int n = matrix[0].length;
        for(int i = 0 ; i < m; i++) {
            if(!check(matrix, i, 0)) return false;
        }
        for(int i =  1; i < n; i++) {
            if(!check(matrix, 0, i)) return false;
        }
        return true;
    }
    
    private boolean check(int [][] matrix, int m, int n) {
        int x = m + 1;
        int y = n + 1;
        while(x < matrix.length && y < matrix[0].length) {
            if(matrix[x][y] != matrix[x-1][y-1]) return false;
            x++;
            y++;
        }
        return true;
    }
}
```

###Conclustion
Runtime beat 93%
Memory beat 46%

###Related Topic
Array