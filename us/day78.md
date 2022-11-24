###question
https://leetcode.com/problems/word-search/
###Solution
```
class Solution {
    public boolean exist(char[][] board, String word) {
        int m = board.length; 
        int n = board[0].length;
        boolean [][] visited = new boolean [m][n];
        for(int i = 0 ; i < m; i++) {
            for(int j = 0 ; j < n; j++) {
                if(board[i][j] == word.charAt(0)) {
                    if(dfs(board, word, 0, i, j, visited)) {
                        return true;
                    }
                }
            }
        }
        return false;
    }
    
    private boolean dfs(char [][] board, String word, int index, int row, int column, boolean [][] visited) {
        if(row < 0 || row >= board.length || column < 0 || column >= board[0].length) return false;
        if(visited[row][column]) return false;
        if(word.charAt(index) == board[row][column]) {
            if(index == word.length() - 1) return true;
            visited[row][column] = true;
            boolean left = dfs(board, word, index + 1, row - 1, column, visited);
            boolean right = dfs(board, word, index + 1, row + 1, column, visited);
            boolean top = dfs(board, word, index + 1, row, column - 1, visited);
            boolean bot = dfs(board, word, index + 1, row, column + 1, visited);
            if(left || right || top || bot) return true;
        }
        visited[row][column] = false;
        return false;
    }
}
```
###Conclustion
Runtime beat 60%
Memory beat 81%

###Related Topic
Array, DFS