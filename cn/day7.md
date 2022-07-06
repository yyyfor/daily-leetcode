###question
https://leetcode.cn/problems/longest-word-in-dictionary-through-deleting/
###Solution
```
class Solution {
    public String findLongestWord(String s, List<String> dictionary) {
        String result = "";
        for(String d: dictionary) {
            String tmp = find(s, d);
            result = compare(tmp, result);
        }
        return result;
    }

    private String find(String s, String d) {
        int a = 0;
        int b = 0;
        if(s.length() < d.length()) return "";
        while(a < s.length() && b < d.length()) {
            if(s.charAt(a) == d.charAt(b)) b++;
            a++;
        }

        if(b == d.length()) return d;
        return "";
    }

    private String compare(String a, String b) {
        if(a.equals(b)) return a;
        int i = 0;
        if(a.length() == 0) return b;
        if(b.length() == 0) return a;
        if(a.length() > b.length()) return a;
        if(a.length() < b.length()) return b;
        while(i < a.length() && i < b.length()) {
            if(a.charAt(i) < b.charAt(i)) return a;
            if(a.charAt(i) > b.charAt(i)) return b;
            i++;
        }
        return "";
    }

}
```

###Conclustion
Runtime beat 84%
Memory beat 8%
通过查字典再比较

###Related Topic
array, two point,sorting