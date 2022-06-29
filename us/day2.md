###question
https://leetcode.com/problems/queue-reconstruction-by-height/
###Solution
```
class Solution {
    public int[][] reconstructQueue(int[][] people) {
        Arrays.sort(people, (o1, o2) -> 
                   o1[0] == o2[0] ? o1[1] - o2[1] : o2[0] - o1[0]);
        List<int []> list = new ArrayList();
        for(int [] array : people) {
            list.add(array[1], array);
        }
        return list.toArray(new int [people.length][2]);
    }
}
```

###Conclustion
Runtime beat 77%
Memory beat 11%
按身高从高到低排序，如果相等按人数从低到高排序。依次插入对应的位置

###Related Topic
Array, Sorting