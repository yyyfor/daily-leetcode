###question
https://leetcode.cn/problems/reformat-the-string/submissions/
###Solution
```
class Solution {
    public String reformat(String s) {
        List<Character> list1 = new ArrayList();
        List<Character> list2 = new ArrayList();
        for(int i = 0 ; i < s.length(); i++) {
            char ch = s.charAt(i);
            if(ch >= '0' && ch <= '9') list1.add(ch);
            else list2.add(ch);
        }
        int diff = list1.size() - list2.size();
        if(diff > 1 || diff < - 1) return "";
        StringBuilder sb = new StringBuilder();
        for(int i = 0 ; i < Math.min(list1.size(), list2.size()); i++) {
            sb.append(list1.get(i));
            sb.append(list2.get(i));
        }
        if(list1.size() > list2.size()) {
            sb.append(list1.get(list1.size() - 1));
        } else if(list1.size() < list2.size()) {
            sb.insert(0, list2.get(list2.size() - 1));
        }
        return sb.toString();

    }
}
```

###Conclustion
Runtime beat 35%
Memory beat 15%

###Related Topic
String