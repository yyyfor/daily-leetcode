###question
https://leetcode.com/problems/number-of-islands/submissions/
###Solution
```
class Solution {
    public int numIslands(char[][] grid) {
        int count = 0;
        for(int i = 0 ; i < grid.length; i++) {
            for(int j = 0; j < grid[0].length; j++) {
                count += helper(grid, i, j);
            }
        }
        return count;
    }
    
    private int helper(char [][] grid, int row, int column) {
        if(row < 0 || column < 0 || row >= grid.length || column >= grid[0].length || grid[row][column] == '0') return 0;
        grid[row][column] = '0';
        helper(grid, row + 1, column);
        helper(grid, row - 1, column);
        helper(grid, row , column + 1);
        helper(grid, row , column - 1);
        return 1;
    }
}
```

###Conclustion
Runtime beat 97%
Memory beat 92%

###Related Topic
Array, DFS