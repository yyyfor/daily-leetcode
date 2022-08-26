###question
https://leetcode.com/problems/reordered-power-of-2/submissions/
###Solution
```
class Solution {
    public boolean reorderedPowerOf2(int n) {
        Map<Integer,Integer> map = calculate(n);
        
        long x = 1;
        while(x <= 1000000000 && x <= 10l * n) {
            Map<Integer,Integer> map2 = calculate(x);
            if(map.equals(map2)) return true;
            x *= 2;
        }
        return false;
        
    }
    
    private Map<Integer,Integer> calculate(long n) {
        Map<Integer,Integer> map = new HashMap();
        while(n != 0) {
            long cur = n % 10;
            map.put((int)cur, map.getOrDefault((int)cur, 0) + 1);
            n /= 10;
        }
        return map;
    }
}
```

there is better hash solution

###Conclustion
Runtime beat 23%
Memory beat 33%

###Related Topic
math, counting