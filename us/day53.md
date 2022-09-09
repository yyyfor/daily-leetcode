###question
https://leetcode.com/problems/the-number-of-weak-characters-in-the-game/
###Solution
```
class Solution {
    public int numberOfWeakCharacters(int[][] properties) {
        Arrays.sort(properties, (o1, o2) -> 
                   o1[0] == o2[0]? o2[1] - o1[1] : o1[0] - o2[0]);
        int count = 0;
        int max = properties[properties.length - 1][1];
        for(int i = properties.length - 2; i >= 0 ; i--) {
            if(properties[i][1] < max) {
                count++;
            } else {
                max = properties[i][1];
            }
        }
        return count;
    }
}
```

###Conclustion
Runtime beat 25%
Memory beat 36%

###Related Topic
Sorting, Array