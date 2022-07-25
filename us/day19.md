###question
https://leetcode.com/problems/find-first-and-last-position-of-element-in-sorted-array
###Solution
```
class Solution {
    public int[] searchRange(int[] nums, int target) {
        int start = 0;
        int end = nums.length - 1;
        int [] result = new int [] {-1, -1};
        if(nums.length == 0) return result;
        
        while(start < end) {
            if(nums[start] == target) break;
            int mid = start + (end - start) / 2;
            if(nums[mid] == target) {
                end--;
            }
            else if(nums[mid] > target) {
                end = mid - 1;
            } else {
                start = mid + 1;
            }
        }
        if(nums[start] != target) return result;
        result[0] = start;
        end = nums.length - 1;
        while(start < end) {
            int mid = start + (end - start) / 2;
            if(nums[mid] == target) {
                start++;
            }
            else if(nums[mid] < target) {
                start = mid + 1;
            } else {
                end = mid - 1;
            }
        }
        result[1] = nums[end] == target ? end : end - 1;
        return result;
        
    }
}
```

###Conclustion
Runtime beat 38%
Memory beat 49%
二分查看过程还可以优化

###Related Topic
Array, Binary search