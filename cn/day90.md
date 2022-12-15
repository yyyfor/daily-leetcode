###question
https://leetcode.cn/problems/sum-of-digits-of-string-after-convert/
###Solution
```
class Solution {
    public int getLucky(String s, int k) {
        List<Integer> list = new ArrayList();
        for(int i = 0 ; i < s.length(); i++) {
            int num = s.charAt(i) - 'a' + 1;
            list.add(num);
        }
        int sum = 0;
        for(int num: list) {
            sum += cal(num);
        }
        for(int i = 0 ; i < k - 1; i++) {
            sum = cal(sum);
        }
        return sum;
    }

    private int cal(int num) {
        int n = 0;
        while(num != 0) {
            n += num % 10;
            num /= 10;
        }
        return n;
    }
}
```


###Conclustion
Runtime beat 79%
Memory beat 33%

###Related Topic
String