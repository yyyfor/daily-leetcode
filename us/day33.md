###question
https://leetcode.com/problems/first-unique-character-in-a-string/submissions/
###Solution
```
class Solution {
    public int firstUniqChar(String s) {
        int [] array = new int [26];
        Arrays.fill(array, -2);
        for(int i = 0 ; i < s.length(); i++) {
            int index = s.charAt(i) - 'a';
            if(array[index] >= 0) {
                array[index] = -1;
            }
            if(array[index] == -2) {
                array[index] = i;
            }
        }
        int min = 1000000;
        for(int i = 0 ; i < 26; i++) {
            if(array[i] >= 0 && array[i] < min) {
                min = array[i];
            }
        }
        min = min == 1000000 ? -1 : min;
        return min;
    }
}
```

###Conclustion
Runtime beat 96%
Memory beat 93%

###Related Topic
Hash table, String, Queue