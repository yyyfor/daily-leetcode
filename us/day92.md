###question
https://leetcode.com/problems/jump-game/description/
###Solution
```
class Solution {
    public boolean canJump(int[] nums) {
        Set<Integer> visited = new HashSet();
        return cal(nums, visited, 0);
    }

    private boolean cal(int [] nums, Set<Integer> visited, int index) {
        if(visited.contains(index)) {
            return false;
        }
        if(index >= nums.length - 1) return true;
        visited.add(index);
        for(int i = 0 ; i <= nums[index]; i++) {
            if(cal(nums, visited, index + i)) {
                return true;
            }
        }
        return false;
    }
}
```


###Conclustion
Runtime beat 5%
Memory beat 36%

###Related Topic
Array, Greedy