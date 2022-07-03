###question
https://leetcode.cn/problems/next-greater-element-iii/
###Solution
```
class Solution {
    public int nextGreaterElement(int n) {
        if(n <= 11) return -1;
        int prev = -1;
        List<Integer> list = new ArrayList();
        while(n > 0) {
            if(prev == -1) {
                prev = n % 10;
                list.add(prev);
                n /= 10;
                continue;
            }

            if(n % 10 >= prev) {
                list.add(n % 10);
                prev = n % 10;
                n /= 10;
            } else {
                list.add(n % 10);
                break;
            }
        }
        if(n == 0) return -1;
        int num = n % 10;
        
        n /= 10;
        Collections.sort(list);
        for(int i = 0 ; i < list.size(); i++) {
            System.out.println(list.get(i));
            if(list.get(i) > num) {
                num = list.get(i);
                break;
            }
        }
        long tmp = n * 10 + num;
        boolean find = false;
        for(int i = 0 ; i < list.size(); i++) {
            
            if(list.get(i) == num && !find) {
                find = true;
                continue;
            }
            
            tmp = tmp * 10 + list.get(i);
            if(tmp > Integer.MAX_VALUE) return -1;
        }
  
        return (int)tmp;
    }
}
```

###Conclustion
Runtime beat 21%
Memory beat 36%
注意考虑边界条件大于Integer.MAX_VALUE

###Related Topic
Math, TWO point