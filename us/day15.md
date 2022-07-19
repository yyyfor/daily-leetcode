###question
https://leetcode.com/problems/pascals-triangle
###Solution
```
class Solution {
    public List<List<Integer>> generate(int numRows) {
        List<Integer> list = new ArrayList();
        List result = new ArrayList();
        result.add(list);
        list.add(1);
        for(int i = 1; i < numRows; i++) {
            List<Integer> tmp = new ArrayList();
            for(int j = 0 ; j <= list.size(); j++) {
                if(j == 0) {
                    tmp.add(list.get(0));
                } else if(j == list.size()) {
                    tmp.add(list.get(list.size() - 1));
                } else {
                    tmp.add(list.get(j - 1) + list.get(j));
                }
            }
            result.add(tmp);
            list = tmp;
        }
        return result;
    }
}
```

###Conclustion
Runtime beat 100%
Memory beat 29%

###Related Topic
Array, dp