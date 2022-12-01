###question
https://leetcode.com/problems/determine-if-string-halves-are-alike/
###Solution
```
class Solution {
    public boolean halvesAreAlike(String s) {
        int num1 = 0;
        int num2 = 0;
        Set<Character> set = new HashSet();
        set.add('a');
        set.add('e');
        set.add('i');
        set.add('o');
        set.add('u');
        set.add('A');
        set.add('E');
        set.add('I');
        set.add('O');
        set.add('U');
        for(int i = 0 ; i < s.length() / 2; i++) {
            char ch = s.charAt(i);
            int j = i + s.length() / 2;
            if(set.contains(ch)) num1++;
            char ch2 = s.charAt(j);
            if(set.contains(ch2)) num2++;
        }
        return num1 == num2;
    }
}
```


###Conclustion
Runtime beat 56%
Memory beat 14%

###Related Topic
String, Counting