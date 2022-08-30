###question
https://leetcode.com/problems/rotate-image/submissions/
###Solution
```
class Solution {
    public void rotate(int[][] matrix) {
        for(int i = 0 ; i < matrix.length; i++) {
            for(int j = i + 1; j < matrix[0].length; j++) {
                int tmp = matrix[i][j];
                matrix[i][j] = matrix[j][i];
                matrix[j][i] = tmp;
            }
        }
        for(int i = 0 ; i < matrix.length; i++) {
            for(int j = 0 ; j < matrix[0].length / 2; j++) {
                int tmp = matrix[i][j];
                matrix[i][j] = matrix[i][matrix[0].length - 1 - j];
                matrix[i][matrix[0].length - 1 - j] = tmp;
            }
        }
    }
}
```

###Conclustion
Runtime beat 100%
Memory beat 65%

###Related Topic
Array, Math