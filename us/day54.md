###question
https://leetcode.com/problems/bag-of-tokens/
###Solution
```
class Solution {
    public int bagOfTokensScore(int[] tokens, int power) {
        if(tokens.length == 0) return 0;
        Arrays.sort(tokens);
        if(tokens[0] > power) return 0;
        int sum = 0;
        int start = 0;
        int length = tokens.length;
        int end = length - 1;
        int count = 0;
        while(start <= end && start < length) {
            while(start < length && power >= tokens[start]) {
                count++;
                power -= tokens[start];
                start++;
            }
            
            if(start < end) {
                power += tokens[end];
                end--;
                count--;
            } else break;
        }
        return count;
    }
}
```

###Conclustion
Runtime beat 20%
Memory beat 76%

###Related Topic
Array, Two point