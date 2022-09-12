###question
https://leetcode.cn/problems/special-array-with-x-elements-greater-than-or-equal-x/
###Solution
```
class Solution {
    public int specialArray(int[] nums) {
        Arrays.sort(nums);
        int start = 0;
        int end = nums[nums.length - 1];
        while(start <= end) {
            int mid = start + (end - start) / 2; 
            int num = search(nums, mid);
            System.out.println(num);
            if(num == mid) return num;
            if(num > mid) {
                start = mid + 1;
            } else {
                end = mid - 1;
            }
        }
        return -1;

    }

    private int search(int [] nums, int num) {
        int start = 0;
        int end = nums.length - 1;
        while(start <= end) {
            int mid = start + (end - start) / 2;
            if(nums[mid] < num) {
                start++;
            } else {
                end--;
            }
        }
        return nums.length - start;
    }
}
```

###Conclustion
Runtime beat 15%
Memory beat 62%

###Related Topic
Array, Sorting