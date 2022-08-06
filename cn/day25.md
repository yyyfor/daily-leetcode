###question
https://leetcode.cn/problems/string-matching-in-an-array/comments/
###Solution
```
class Solution {
    public List<String> stringMatching(String[] words) {
        Set<String> list = new HashSet();
        for(int i = 0 ; i < words.length; i++) {
            for(int j = 0; j < words.length; j++) {
                if(i == j) continue;
                if(words[j].indexOf(words[i]) != -1) {
                    list.add(words[i]);
                }
            }
        }
        return new ArrayList(list);
    }
}
```

###Conclustion
Runtime beat 64%
Memory beat 19%

double loop

###Related Topic
String