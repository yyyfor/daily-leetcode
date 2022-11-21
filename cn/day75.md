###question
https://leetcode.cn/problems/soup-servings/description/
###Solution
```
class Solution {
    public double soupServings(int n) {
        Map<String, Double> map = new HashMap();
        return dfs(n, n, map);
    }

    private double dfs(int a, int b, Map<String, Double> map) {
        if(a >= 5000) return 1d;
        if(map.containsKey(a + "_" + b)) return map.get(a + "_" + b);
        if(a == 0 && b == 0) return 0.5;
        if(a == 0) return 1d;
        if(b == 0) return 0d;
        double prob = 0;
        prob += dfs(Math.max(0, a - 100), b, map);
        prob += dfs(Math.max(0, a - 75), Math.max(0, b - 25), map);
        prob += dfs(Math.max(0, a - 50), Math.max(0, b - 50), map);
        prob += dfs(Math.max(0, a - 25), Math.max(0, b - 75), map);
        prob *= 0.25;
        map.put(a + "_" + b, prob);
        return prob;
    }
}
```
add hashmap for remove duplicate
###Conclustion
Runtime beat 7%
Memory beat 7%

###Related Topic
math