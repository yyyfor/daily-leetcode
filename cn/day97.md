###question
https://leetcode.cn/problems/count-nice-pairs-in-an-array/submissions/395911098/
###Solution
```
class Solution {
    public int countNicePairs(int[] nums) {
        Map<Integer, Integer> map = new HashMap();
        for(int num : nums) {
            map.put(num, reverse(num));
        }
        int result = 0;
        for(int i = 0 ; i < nums.length; i++) {
            int rev = reverse(nums[i]);
            System.out.println(rev);
            result += map.getOrDefault(rev, 0);
            result %= 1000000007;
            map.put(rev, map.getOrDefault(rev, 0) + 1);
        }
        return result;
    }

    private int reverse (int num) {
        int tmp = num;
        int result = 0;
        while(num != 0) {
            result = result * 10 + (num % 10);
            num /= 10;
        }
        return tmp - result;
    }
}
```


###Conclustion
Runtime beat 5%
Memory beat 38%

###Related Topic
Map