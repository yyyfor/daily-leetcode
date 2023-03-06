### question
https://leetcode.com/problems/removing-minimum-and-maximum-from-array/
### Solution
```
class Solution {
    public int minimumDeletions(int[] nums) {
        if(nums.length <= 1) return 1;
        int minIndex = -1;
        int maxIndex = -1;
        int max = Integer.MIN_VALUE;
        int min = Integer.MAX_VALUE;
        for(int i = 0; i < nums.length; i++) {
            if(nums[i] > max) {
                max = nums[i];
                maxIndex = i;
            }
            if(nums[i] < min) {
                min = nums[i];
                minIndex = i;
            }
        }
        int result = 0;
        System.out.println(minIndex);
        System.out.println(maxIndex);
    
        if(minIndex < maxIndex) {
            if(minIndex + 1 < nums.length - maxIndex) {
                result += minIndex + 1;
                result += Math.min(maxIndex - minIndex, nums.length - maxIndex);
            } else {
                result += nums.length - maxIndex;
                result += Math.min(minIndex + 1, maxIndex - minIndex);
            }
        } else {
            if(maxIndex + 1 < nums.length - minIndex) {
                result += maxIndex + 1;
                result += Math.min(minIndex - maxIndex, nums.length - minIndex);
            } else {
                result += nums.length - minIndex;
                result += Math.min(maxIndex + 1, minIndex - maxIndex);
            }
        }
        return result;
    }
}
```

### Conclustion
Runtime beat 12%
Memory beat 68%

### Related Topic
Greedy, Array