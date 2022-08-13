###question
https://leetcode.cn/problems/max-chunks-to-make-sorted/
###Solution
```
class Solution {
    public int maxChunksToSorted(int[] arr) {
        int count = 0;
        int max = 0;
        for(int i = 0; i < arr.length; i++) {
            max = Math.max(max, arr[i]);
            if(max == i) count++;
        }
        return count;
    }
}
```

###Conclustion
Runtime beat 100%
Memory beat 22%

###Related Topic
Stack, Array