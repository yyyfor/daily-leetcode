### question
https://leetcode.cn/problems/wiggle-sort-ii/
### Solution
```
class Solution {
    public void wiggleSort(int[] nums) {
        int [] result = new int [nums.length];
        Arrays.sort(nums);
        int index = 1;
        int end = nums.length - 1;
        while(index < nums.length) {
            result[index] = nums[end];
            end--;
            index += 2;
        }
        index = 0;
        while(index < nums.length) {
            result[index] = nums[end];
            end--;
            index += 2;
        }
        for(int i = 0 ; i < nums.length; i++) {
            nums[i] = result[i];
        }
    }
}
```

### Conclustion
- Runtime beat 73%
- Memory beat 53%
做题的时候应该反向存放最大数据，避免中间数据和两个最小数据相邻

### Related Topic
Array, QuickSelect, Sorting