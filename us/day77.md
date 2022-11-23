###question
https://leetcode.com/problems/valid-sudoku/
###Solution
```
class Solution {
    public boolean isValidSudoku(char[][] board) {
        for(int i = 0 ; i < board.length; i++) {
            if(!column(board, i)) return false;
        }
        
        for(int i = 0 ; i < board[0].length; i++) {
            if(!row(board, i)) return false;
        }
        for(int i = 0 ; i < 9; i = i + 3) {
            for(int j = 0 ; j < 9; j = j + 3) {
                if(!box(board, i, j)) return false;
            }
        }
        return true;
    }
    
    private boolean column(char [][] board, int column) {
        Set<Integer> set = new HashSet();
        for(int i = 0 ; i < board.length; i++) {
            if(board[i][column] == '.') continue;
            int num = board[i][column] - '0';
            if(!set.add(num)) {
                System.out.println("column " + num);
                return false;
            }
        }
        return true;
    }
    
    private boolean box(char [][] board, int row, int column) {
        Set<Integer> set = new HashSet();
        for(int i = row; i <= row + 2; i++) {
            for(int j = column; j <= column + 2; j++) {
                System.out.println(j);
                if(board[i][j] == '.') continue;
                int num = board[i][j] - '0';
                if(!set.add(num)) {
                System.out.println("box " + num);
                return false;
            }
            }
        }
        return true;
    }
    
    private boolean row(char [][] board, int row) {
        Set<Integer> set = new HashSet();
        for(int i = 0 ; i < board[0].length; i++) {
            if(board[row][i] == '.') continue;
            int num = board[row][i] - '0';
            if(!set.add(num)) {
                System.out.println("row " + num);
                return false;
            }
        }
        return true;
    }
}
```
###Conclustion
Runtime beat 9%
Memory beat 88%

###Related Topic
Array, hash table