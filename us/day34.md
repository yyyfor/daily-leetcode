###question
https://leetcode.com/problems/unique-morse-code-words/
###Solution
```
class Solution {
    public int uniqueMorseRepresentations(String[] words) {
        String [] map = new String [] { ".-","-...","-.-.","-..",".","..-.","--.","....","..",".---","-.-",".-..","--","-.","---",".--.","--.-",".-.","...","-","..-","...-",".--","-..-","-.--","--.." };
        Set<String> set = new HashSet();
        for(String word: words) {
            String s = new String();
            for(int i = 0 ; i < word.length(); i++) {
                int index = word.charAt(i) - 'a';
                s += map[index];
            }
            if(set.add(s));
        }
        return set.size();
    }
}
```

###Conclustion
Runtime beat 34%
Memory beat 78%

###Related Topic
Array, Hash Table