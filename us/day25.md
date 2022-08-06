###question
https://leetcode.com/problems/smallest-value-of-the-rearranged-number/submissions/
###Solution
```
class Solution {
    public long smallestNumber(long num) {
        if(num == 0) return 0;
        boolean negative = num < 0;
        List<Long> list = new ArrayList();
        num = Math.abs(num);
        while(num != 0) {
            list.add(num % 10);
            num /= 10;
        }
        Collections.sort(list);
        long result = 0;
        int numOfZero = 0;
        if(negative) {
            for(int i = list.size() - 1; i >= 0; i--) {
                result = result * 10 + list.get(i);
                // System.out.println(result);
            }
            result = -1 * result;
        } else {
            int i = 0;
            for(; i < list.size(); i++) {
                if(list.get(i) == 0) numOfZero++;
                else break;
            }
            result = list.get(i);
            i++;
            for(int j = 0 ; j < numOfZero; j++) {
                result *= 10;
            }
            for( ; i < list.size(); i++) {
                result = result * 10 + list.get(i);
            }
        }
        return result;
    }
}
```

###Conclustion
Runtime beat 57%
Memory beat 77%

###Related Topic
Math, sorting