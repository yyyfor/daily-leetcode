###question
https://leetcode.com/problems/valid-anagram
###Solution
```
class Solution {
    public boolean isAnagram(String s, String t) {
        if(s.length() != t.length()) return false;
        int [] chars = new int [26];
        for(char ch : s.toCharArray()) {
            chars[ch - 'a']++;
        }
        for(char ch : t.toCharArray()) {
            chars[ch - 'a']--;
            if(chars[ch - 'a'] < 0) return false;
        }
        for(int i = 0 ; i < 26; i++) {
            if(chars[i] != 0) return false;
        }
        return true;
    }
}
```

###Conclustion
Runtime beat 95%
Memory beat 47%

###Related Topic
Hash Table, String