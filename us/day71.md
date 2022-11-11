###question
https://leetcode.com/problems/remove-duplicates-from-sorted-array/
###Solution
```
class Solution {
    public int removeDuplicates(int[] nums) {
        List<Integer> list = new ArrayList();
        for(int num : nums) {
            if(list.isEmpty() || num != list.get(list.size() - 1)) {
                list.add(num);
            }
        }
        for(int i = 0 ; i < list.size(); i++) {
            nums[i] = list.get(i);
        }
        return list.size();
    }
}
```
use a pointer could be better

###Conclustion
Runtime beat 16%
Memory beat 26%

###Related Topic
Array, two pointer