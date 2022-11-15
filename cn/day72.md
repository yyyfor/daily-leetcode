###question
https://leetcode.cn/problems/maximum-units-on-a-truck/discussion/
###Solution
```
class Solution {
    public int maximumUnits(int[][] boxTypes, int truckSize) {
        Arrays.sort(boxTypes, (o1 ,o2) -> o2[1] - o1[1]);
        int total = 0;
        for(int i = 0 ; i < boxTypes.length; i++) {
            int [] box = boxTypes[i];
            if(truckSize > box[0]) {
                truckSize -= box[0];
                total += box[0] * box[1];
            } else {
                total += box[1] * truckSize;
                return total;
            }
        }
        return total;
    }
}
```

###Conclustion
Runtime beat 91%
Memory beat 34%

###Related Topic
Greedy