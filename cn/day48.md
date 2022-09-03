###question
https://leetcode.cn/problems/maximum-length-of-pair-chain/submissions/
###Solution
```
class Solution {
    public int findLongestChain(int[][] pairs) {
        Arrays.sort(pairs, (o1, o2) -> 
            o1[0] - o2[0]
        );
        int num = 1;
        int last = pairs[0][1];
        for(int i = 1; i < pairs.length; i++) {
            if(pairs[i][0] > last) {
                num++;
                last = pairs[i][1];
            } else if(pairs[i][1] < last) {
                last = pairs[i][1];
            }
        }
        return num;
    }
}
```
think about dp. BFS is not efficient

###Conclustion
Runtime beat 98%
Memory beat 35%

###Related Topic
DP, Sorting