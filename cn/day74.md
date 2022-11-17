###question
https://leetcode.cn/problems/number-of-matching-subsequences/discussion/
###Solution
```
class Solution {
    Map<String, Boolean> map;
    public int numMatchingSubseq(String s, String[] words) {
        int count = 0;
        map = new HashMap();
        for(String word: words) {
            if(match(s, word)) count++;
        }
        return count;
    }

    private boolean match(String s1, String s2) {
        if(s1.length() < s2.length()) return false;
        if(map.containsKey(s2)) return map.get(s2);
        int index = 0;
        for(int i = 0 ; i < s1.length() && index < s2.length(); i++) {
            if(s1.charAt(i) == s2.charAt(index)) index++;
        }
        boolean m = s2.length() == index;
        map.put(s2, m);
        return m;
    }
}
```
add hashmap for remove duplicate
###Conclustion
Runtime beat 59%
Memory beat 99%

###Related Topic
String, hash table