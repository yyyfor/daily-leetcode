###question
https://leetcode.com/problems/binary-trees-with-factors/submissions/
###Solution
```
class Solution {
    public int numFactoredBinaryTrees(int[] arr) {
        Arrays.sort(arr);
        Map<Integer, Long> map = new HashMap();
        for(int num : arr) {
            map.put(num, 1l);
        }
        
        for(int num : arr) {
            for(int num2 : map.keySet()) {
                if(num % num2 == 0 && map.containsKey(num / num2)) {
                    map.put(num, map.get(num) + map.get(num2) * map.get(num / num2));
                }
            }
        }
        long sum = 0;
        for (Integer n : map.keySet()) {
            sum = (sum + map.get(n)) % ((int) Math.pow(10, 9) + 7) ;
        }
        return (int)sum;
    }
}
```

###Conclustion
Runtime beat 20%
Memory beat 93%

be cautious when cast long to int and do mod operation

###Related Topic
Array, Dp, Hash table