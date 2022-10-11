###question
https://leetcode.cn/problems/check-if-one-string-swap-can-make-strings-equal/submissions/
###Solution
```
class Solution {
    public boolean areAlmostEqual(String s1, String s2) {
        if (s1.length() != s2.length()) return false;
        int count = 0, m = -1, n = -1;
        for (int i = 0, j = 0; i < s1.length(); i++, j++) {
            if (s1.charAt(i) != s2.charAt(j)) {
                count++;
                if (m == -1) m = i;
                if (n == -1 && m != i) n = i;
            }
        }
        if (count == 0) return true;
        if (count == 2 && s1.charAt(m) == s2.charAt(n) && s2.charAt(m) == s1.charAt(n))
            return true;
        return false;
    }
}
```

###Conclustion
Runtime beat 100%
Memory beat 96%
use two sign to record

###Related Topic
String