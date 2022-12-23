###question
https://leetcode.com/problems/goat-latin/submissions/864182085/
###Solution
```
class Solution {
    public String toGoatLatin(String sentence) {
        String [] strs = sentence.split(" ");
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
        StringBuilder sb = new StringBuilder();
        int index = 1;
        for(int i = 0 ; i < strs.length; i++) {
            String s = strs[i];
            char ch = s.charAt(0);
            if(set.contains(ch)) {
                sb.append(s);
                sb.append("ma");
            } else {
                sb.append(s.substring(1));
                sb.append(ch);
                sb.append("ma");
            }
            for(int j = 0; j < index; j++) {
                sb.append("a");
            }
            sb.append(" ");
            index++;
        }
        return sb.toString().trim();
    }
}
```


###Conclustion
Runtime beat 72%
Memory beat 63%

###Related Topic
String