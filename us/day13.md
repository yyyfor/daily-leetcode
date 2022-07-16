###question
https://leetcode.com/problems/out-of-boundary-paths/
###Solution
```
class Solution {
    public int findPaths(int m, int n, int maxMove, int startRow, int startColumn) {
        if(maxMove == 0) return 0;
        int [][][] visited = new int [m][n][maxMove + 1];
        for(int i = 0; i < m; i++) {
            for(int j = 0 ; j < n; j++) {
                for(int z = 0 ; z < maxMove; z++) {
                    visited[i][j][z] = -1;
                }
            }
        }
        return helper(startRow, startColumn, visited, m, n, maxMove, 0);
    }
    
    private int helper(int row, int col, int [][][] visited, int m, int n, int maxMove, int index) {
        if(row < 0 || row >= m || col < 0 || col >= n) return 1;
        if(visited[row][col][index] != -1) return visited[row][col][index];
        if(index == maxMove) return 0;
        long left = helper(row, col - 1, visited, m, n, maxMove, index + 1);
        long right = helper(row, col + 1, visited, m, n, maxMove, index + 1);
        long bot = helper(row - 1, col , visited, m, n, maxMove, index + 1);
        long up = helper(row + 1, col , visited, m, n, maxMove, index + 1);
        long sum = left + right + bot + up;
        sum %= 1000000007;
        visited[row][col][index] = (int)sum;
        return (int)sum;
    }
}
```

###Conclustion
Runtime beat 85%
Memory beat 58%
使用3维数组记录move的状态
结果转成long进行计算再cast to int

###Related Topic
dfs, memorization