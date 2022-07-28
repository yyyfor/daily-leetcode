###question
https://leetcode.cn/problems/rank-transform-of-an-array/submissions/
###Solution
```
class Solution {
    public int[] arrayRankTransform(int[] arr) {
        if(arr.length == 0) return arr;
        int [] r = Arrays.copyOf(arr, arr.length);
        Arrays.sort(arr);
        Map<Integer,Integer> map = new HashMap();
        int index = 1;
        map.put(arr[0],index++);
        for(int i = 1; i < arr.length; i++) {
            if(!map.containsKey(arr[i])) {
                map.put(arr[i], index++);
            }
        }

        for(int i = 0 ; i < r.length; i++) {
            arr[i] = map.get(r[i]);
        }
        return arr;
    }
}
```

###Conclustion
Runtime beat 37%
Memory beat 31%

###Related Topic
Hash Table, Array