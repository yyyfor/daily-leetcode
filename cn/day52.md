###question
https://leetcode.cn/problems/rearrange-spaces-between-words/
###Solution
```
class Solution {
    public String reorderSpaces(String text) {
        int space = 0;
        for(char ch : text.toCharArray()) {
            if(ch == ' ') space++;
        }
        if(space == 0) return text;
        String [] strs = text.trim().split("\\s+");
        
        StringBuilder sb = new StringBuilder();
        for(int j = 0; j < strs.length; j++) {
            String str = strs[j];
            sb.append(str);
            if(j == strs.length - 1) continue;
            for(int i = 0 ; i < space / (strs.length - 1); i++) {
                sb.append(" ");
            }
        }
        if(strs.length == 1 || space % (strs.length - 1) != 0) {
            if(strs.length == 1) {
                for(int i = 0 ; i < space; i++) {
                    sb.append(" ");
                }
            } else {
                for(int i = 0 ; i < space % (strs.length - 1); i++) {
                    sb.append(" ");
                }
            }
            
        }
        return sb.toString();
    }
}
```

###Conclustion
Runtime beat 31%
Memory beat 77%

###Related Topic
String