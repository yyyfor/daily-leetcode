###question
https://leetcode.cn/problems/count-number-of-homogenous-substrings/description/
###Solution
```
class Solution {
    public int countHomogenous(String s) {
        int count = 0;
        int index = 1;
        for(int i = 0 ; i < s.length(); i++) {
            if(i == 0) {
                count += index;
                continue;
            }
            if(s.charAt(i) == s.charAt(i - 1)) {
                index++;
            } else {
                index = 1;
            }
            count += index;
            count %= (1000000007);
        }
        return count;
    }
}
```


###Conclustion
Runtime beat 18%
Memory beat 36%

###Related Topic
String, Math