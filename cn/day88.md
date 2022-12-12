###question
https://leetcode.cn/problems/sum-of-beauty-of-all-substrings/submissions/388655366/
###Solution
```
class Solution {
    public int beautySum(String s) {
        int res = 0;
        for (int i = 0; i < s.length(); i++) {
            int[] cnt = new int[26];
            int maxFreq = 0;
            for (int j = i; j < s.length(); j++) {
                cnt[s.charAt(j) - 'a']++;
                maxFreq = Math.max(maxFreq, cnt[s.charAt(j) - 'a']);
                int minFreq = s.length();
                for (int k = 0; k < 26; k++) {
                    if (cnt[k] > 0) {
                        minFreq = Math.min(minFreq, cnt[k]);
                    }
                }
                res += maxFreq - minFreq;
            }
        }
        return res;
    }

    private int cal(String s, int i, int j) {
        int [] array = new int [26];
        int max = 0;
        int min = s.length();
        for(int m = i ; m <= j; m++) {
            char ch = s.charAt(m);
            int index = ch - 'a';
            array[index]++;
            if(array[index] > max) {
                max = array[index];
            }
            
        }
        for(int k = 0; k < 26; k++) {
            if(array[k] > 0 && array[k] < min) {
                min = array[k];
            }
        }
        return max - min;
    }
}
```


###Conclustion
Runtime beat 61%
Memory beat 79%

###Related Topic
Hash table, String