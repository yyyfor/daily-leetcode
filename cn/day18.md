###question
https://leetcode.cn/problems/divide-a-string-into-groups-of-size-k/comments/
###Solution
```
class Solution {
    public String[] divideString(String s, int k, char fill) {
        String [] array = new String [(s.length() + k - 1) / k];
        for(int i = 0 ; i < array.length; ) {
            array[i] = s.substring(i * k, Math.min(s.length(), (i + 1) * k));
            i++;
        }

        if(array[array.length - 1].length() != k) {
            for(int i = array[array.length - 1].length(); i < k; i++) {
                array[array.length - 1] += fill;
            }
        }
        return array;
    }
}
```

###Conclustion
Runtime beat 20%
Memory beat 5%
用list效率更高

###Related Topic
String