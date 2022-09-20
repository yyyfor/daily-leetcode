###question
https://leetcode.cn/problems/partition-to-k-equal-sum-subsets/
###Solution
```
class Solution {
    public boolean canPartitionKSubsets(int[] nums, int k) {
        int sum = 0;
        for(int num: nums) {
            sum += num;
        }
        if(sum % k != 0) return false;
        Arrays.sort(nums);
        sum = sum / k;
        int [] arr = new int [k];
        Arrays.fill(arr, sum);
        return helper(nums, nums.length - 1, arr, k);
    }

    private boolean helper(int [] nums, int index, int [] arr, int k) {
        if(index < 0) return true;
        for(int i = 0 ; i < k; i++) {
            if(arr[i] == nums[index]  || (index > 0 && arr[i] - nums[index] >= nums[0])) {
                arr[i] -= nums[index];
                if(helper(nums, index - 1, arr, k) ) {
                    return true;
                }

                arr[i] += nums[index];
            }
        }
        return false;
        
        
    }
}
```

###Conclustion
Runtime beat 6%
Memory beat 88%

###Related Topic
Array, Back tracking