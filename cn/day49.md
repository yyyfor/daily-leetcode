###question
https://leetcode.cn/problems/special-positions-in-a-binary-matrix/submissions/
###Solution
```
class Solution {
    public int numSpecial(int[][] mat) {
        int count = 0;
        for(int i = 0 ; i < mat.length; i++) {
            for(int j = 0 ; j < mat[0].length; j++) {
                if(mat[i][j] == 1 && isSpecial(mat, i, j)) count++;
            }
        }
        return count;
    }

    private boolean isSpecial(int [][] mat, int row, int column) {
        for(int i = 0 ; i < mat.length; i++) {
            if(i != row && mat[i][column] == 1) return false;
        }
        for(int i = 0 ; i < mat[0].length; i++) {
            if(i != column && mat[row][i] == 1) return false;
        }
        return true;
    }
}
```

###Conclustion
Runtime beat 100%
Memory beat 85%

###Related Topic
Array