###question
https://leetcode.cn/problems/shuffle-the-array/comments/
###Solution
```
class Solution {
    public int[] shuffle(int[] nums, int n) {
        List<Integer> list = new ArrayList();
        for(int i = 0 ; i < n; i++) {
            list.add(nums[i]);
            list.add(nums[n + i]);
        }
        for(int i = 0 ; i < 2 * n; i++) {
            nums[i] = list.get(i);
        }
        return nums;
    }
}
```

###Conclustion
Runtime beat 11%
Memory beat 15%

###Related Topic
Array