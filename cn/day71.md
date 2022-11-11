###question
https://leetcode.cn/problems/determine-if-string-halves-are-alike/
###Solution
```
class Solution {
    public boolean halvesAreAlike(String s) {
        if(s.length() % 2 != 0) return false;
        Set<Character> set = new HashSet();
        set.add('a');
        set.add('A');
        set.add('E');
        set.add('I');
        set.add('O');
        set.add('U');
        set.add('e');
        set.add('i');
        set.add('o');
        set.add('u');
        return count(set, 0, s.length() / 2, s) == count(set, s.length() / 2, s.length(), s);
    }

    private int count(Set<Character> set, int start, int end,String s) {
        int count = 0;
        for(int i = start ; i < end; i++) {
            if(set.contains(s.charAt(i))) count++;
        }
        return count;
    }
}
```

###Conclustion
Runtime beat 95%
Memory beat 44%

###Related Topic
String