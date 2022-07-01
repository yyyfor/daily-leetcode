###question
https://leetcode.com/problems/maximum-units-on-a-truck/
###Solution
```
class Solution {
    public int maximumUnits(int[][] boxTypes, int truckSize) {
        Arrays.sort(boxTypes, (o1 , o2) -> o2[1] - o1[1]);
        int sum = 0;
        for(int i = 0 ; i < boxTypes.length; i++) {
            int [] box = boxTypes[i];
            if(box[0] >= truckSize) {
                sum += truckSize * box[1];
                return sum;
            } else {
                truckSize -= box[0];
                sum += box[1] * box[0];
            }
        }
        return sum;
    }
}
```

###Conclustion
Runtime beat 93%
Memory beat 90%
先根据值排序，再按数量取

###Related Topic
Array, Greedy, Sort