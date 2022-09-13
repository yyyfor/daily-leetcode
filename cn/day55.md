###question
https://leetcode.cn/problems/maximum-swap/
###Solution
```
class Solution {
    public int maximumSwap(int num) {
        if(num <= 11) return num;
        List<Integer> list = new ArrayList();
        while(num != 0) {
            list.add(num % 10);
            num /= 10;
        }
        for(int i = list.size() - 1; i > 0; i--) {
            int [] max = new int [] {0, 0};
            for(int j = 0; j < i; j++) {
                if(list.get(j) > max[0]) {
                    max[0] = list.get(j);
                    max[1] = j;
                }
            }
            if(max[0] > list.get(i)) {
                list.set(max[1], list.get(i));
                list.set(i, max[0]);
                break;
            }
        }
        
        int result = 0;
        for(int i = list.size() - 1; i >= 0; i--) {
            result = 10 * result + list.get(i);
        }
        return result;

    }
}
```
check max for better performance

###Conclustion
Runtime beat 38%
Memory beat 82%

###Related Topic
Array, Greedy