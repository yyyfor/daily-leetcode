###question
https://leetcode.com/problems/ransom-note/
###Solution
```
class Solution {
    public boolean canConstruct(String ransomNote, String magazine) {
        Map<Character,Integer> map = new HashMap();
        for(char ch: magazine.toCharArray()) {
            map.put(ch, map.getOrDefault(ch, 0) + 1);
        }
        for(char ch : ransomNote.toCharArray()) {
            if(!map.containsKey(ch)) return false;
            int count = map.get(ch) - 1;
            if(count < 0) return false;
            map.put(ch, count);
        }
        return true;
    }
}
```

###Conclustion
Runtime beat 27%
Memory beat 24%

###Related Topic
Array, Map