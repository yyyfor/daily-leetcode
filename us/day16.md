###question
https://leetcode.com/problems/number-of-matching-subsequences

###Solution
```
class Solution {
    public int numMatchingSubseq(String s, String[] words) {
        int count = 0;
        Set<String> set = new HashSet();
        Set<String> set2 = new HashSet();
        for(String word : words) {
            if(set.contains(word)) {
                count++;
                continue;
            }
            if(set2.contains(word)) {
                continue;
            }
            if(match(s,word)) {
                count++;
                set.add(word);
            } else {
                set2.add(word);
            }
        }
        return count;
    }
    
    private boolean match(String s, String word) {
        int i1 = 0;
        int i2 = 0;
        if(s.length() < word.length()) return false;
        while(i2 != word.length() && i1 != s.length()) {
            if(s.charAt(i1) == word.charAt(i2)) {
                i2++;
            }
            i1++;
        }
        return i2 == word.length();
    }
}
```

###Conclustion
Runtime beat 52%
Memory beat 78%
注意记录已经处理过的string

###Related Topic
String, Hash table