###question
https://leetcode.com/problems/interleaving-string/
###Solution
```
class Solution {
    public boolean isInterleave(String s1, String s2, String s3) {
        if(s1.length() + s2.length() != s3.length()) return false;
        return valid(s1,s2,s3,0,0,0,new boolean [s1.length() + 1][s2.length() + 1]);
    }
    
    private boolean valid(String s1, String s2, String s3,
                         int index1, int index2, int index3,
                         boolean [][] isValid) {
        if(isValid[index1][index2]) return false;
        if(index3 == s3.length()) return true;
        boolean v = false;
        if(index1 < s1.length() && s1.charAt(index1) == s3.charAt(index3) && valid(s1,s2,s3,index1 + 1, index2, index3 + 1, isValid) || index2 < s2.length() && s2.charAt(index2) == s3.charAt(index3) && valid(s1,s2,s3,index1, index2 + 1, index3 + 1, isValid)) {
            return true;
        }
        isValid[index1][index2] = true;
        return false;
        
    }
}
```

###Conclustion
Runtime beat 99%
Memory beat 42%
dfs.使用dp数组记录计算过的值

###Related Topic
array,dp