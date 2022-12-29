###question
https://leetcode.cn/problems/two-out-of-three/submissions/391702814/
###Solution
```
class Solution {
    public List<Integer> twoOutOfThree(int[] nums1, int[] nums2, int[] nums3) {
        Set<Integer> set1 = new HashSet();
        Set<Integer> set2 = new HashSet();
        Set<Integer> set3 = new HashSet();
        Set<Integer> list = new HashSet();
        for(int num: nums1) {
            set1.add(num);
        }
        for(int num: nums2) {
            set2.add(num);
        }
        for(int num: nums3) {
            set3.add(num);
        }
        for(int num: nums1) {
            if(set2.contains(num) || set3.contains(num))
            list.add(num);
        }
        for(int num: nums2) {
            if(set1.contains(num) || set3.contains(num))
            list.add(num);
        }
        for(int num: nums3) {
            if(set2.contains(num) || set1.contains(num))
            list.add(num);
        }
        return new ArrayList(list);
    }
}
```


###Conclustion
Runtime beat 44%
Memory beat 60%

###Related Topic
PriorityQueue