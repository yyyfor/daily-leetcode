###question
https://leetcode.cn/problems/3sum/submissions/
###Solution
```
class Solution {
    public List<List<Integer>> threeSum(int[] nums) {
        List<List<Integer>> r = new ArrayList();
        Arrays.sort(nums);
        for(int i = 0 ; i < nums.length - 2; i++) {
            if(i != 0 && nums[i] == nums[i - 1]) continue;
            int left = i + 1;
            int right = nums.length - 1;
            while(left < right) {
                if(nums[i] + nums[left] + nums[right] == 0) {
                    List<Integer> list = new ArrayList();
                    list.add(nums[i]);
                    list.add(nums[left]);
                    list.add(nums[right]);
                    r.add(list);
                    left++;
                    while(nums[left] == nums[left - 1] && left < right) left++;
                    right--;
                    while(nums[right] == nums[right + 1] && left < right) right--;
                }
                else if(nums[i] + nums[left] + nums[right] > 0) {
                    right--;
                } else {
                    left++;
                }
            }
        }
        return r;
    }
}
```

###Conclustion
Runtime beat 41%
Memory beat 23%

###Related Topic
Array, sorting