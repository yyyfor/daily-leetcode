###question
https://leetcode.com/problems/utf-8-validation/
###Solution
```
class Solution {
    public boolean validUtf8(int[] data) {
        for(int i = 0; i < data.length; ) {
            int type = type(data[i]);
            System.out.println(type);
            if(type == 5 || type == -1) return false;
            int j = i + type;
            for(int m = i + 1; m < j; m++) {
                if(m >= data.length || type(data[m]) != 5) return false;
            }
            i = j;
        }
        return true;
    }
    
    private int type(int data) {
        List<Integer> list = new ArrayList();
        while(data != 0) {
            list.add(0, data % 2);
            data /= 2;
        }
        while(list.size() != 8) {
            list.add(0, 0);
        }
        if(list.get(0) == 0) return 1;
        if(list.get(1) == 0) return 5;
        if(list.get(1) == 1 && list.get(2) == 0) return 2;
        if(list.get(1) == 1 && list.get(2) == 1 && list.get(3) == 0) return 3;
        if(list.get(1) == 1 && list.get(2) == 1 && list.get(3) == 1 && list.get(4) == 0) return 4;
        return -1;
        
    }
}
```
use mask to get type for better performance

###Conclustion
Runtime beat 8%
Memory beat 8%

###Related Topic
Array, Bit manipulation