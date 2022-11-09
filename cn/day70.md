###question
https://leetcode.cn/problems/largest-plus-sign/
###Solution
```
class Solution {
    public int orderOfLargestPlusSign(int n, int[][] mines) {
        int [][] g = new int [n][n];
        for(int [] array : mines) {
            g[array[0]][array[1]] = 1;
        }
        int max = 0;
        for(int i = 0 ; i < n; i++) {
            for(int j = 0 ; j < n; j++) {
                max = Math.max(max, check(i, j, g, n));
            }
        }
        return max;
    }

    private int check(int i, int j, int [][] g, int n) {
        if(g[i][j] == 1) return 0;
        int up=0;
        int left=0;
        int right=0;
        int down=0;
        for (int k=i;k>=0;k--) if (g[k][j]==0)up++; else break;
        for (int k=i;k<n;k++) if (g[k][j]==0)down++; else break;
        for (int k=j;k>=0;k--)if (g[i][k]==0)left++; else break;
        for (int k=j;k<n;k++) if (g[i][k]==0)right++; else break;
        int cur=Math.min(up,left);
        int cur2=Math.min(right,down);
        int cur3=Math.min(cur,cur2);
        return cur3;
    }
}
```

###Conclustion
Runtime beat 6%
Memory beat 94%

###Related Topic
Brutal force