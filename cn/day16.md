###question
https://leetcode.cn/problems/shift-2d-grid/
###Solution
```
class Solution {
    public List<List<Integer>> shiftGrid(int[][] grid, int k) {
        int m = grid.length;
        int n = grid[0].length;
        int [] array = new int [m * n];
        k = k % (m * n);
        List result = new ArrayList();
        List<Integer> list = new ArrayList();
        for(int i = 0 ; i < m ; i++) {
            for(int j = 0 ; j < n; j++) {
                System.out.println((i * n + j));
                array[(i * n + j) % (m * n)] = grid[i][j];
            }
        }
        for(int num : array) System.out.println(num);
        for(int i = m * n - k ; i < m * n ; i++) {
            list.add(array[i]);
            if(list.size() == n) {
                result.add(list);
                list = new ArrayList();
            }
        }
        
        for(int i = 0 ; i < m * n - k ; i++) {
            list.add(array[i]);
            if(list.size() == n) {
                result.add(list);
                list = new ArrayList();
            }
        }
        return result;
    }
}
```

###Conclustion
Runtime beat 5%
Memory beat 55%
二维数组先转换为一维

###Related Topic
Array, Matrix