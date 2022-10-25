###question
https://leetcode.com/problems/maximum-length-of-a-concatenated-string-with-unique-characters/
###Solution
```
class Solution {
    public int maxLength(List<String> arr) {
        List<Long> list = new ArrayList();
        for(String s: arr) {
            list.add(transfer(s));
        }
        return dfs(list, 0, 0);
        
    }
    
    private int dfs(List<Long> list, int index, long num) {
        if(index == list.size()) {
            return count(num);
        }
        long cur = list.get(index);
        int count = 0;
        long r = num & cur;
        if(r == 0) {
            count = dfs(list, index + 1, num | cur);
        }
        count = Math.max(count, dfs(list, index + 1, cur));
        count = Math.max(count, dfs(list, index + 1, num));
        return count;       
    }
    
    private int count(long num) {
        int count = 0;
        while(num != 0) {
            num = num & (num - 1);
            count++;
        }
        return count;
    }
    private long transfer(String s) {
        long num = 0;
        for(int i = 0 ; i < s.length(); i++) {
            int index = s.charAt(i) - 'a';
            if((num & (1 << index)) != 0) {
                System.out.println("a");
                return 0;
            }
            num |= 1 << index;
        }
        return num;
    }
}

```

###Conclustion
Runtime beat 7%
Memory beat 98%

###Related Topic
DFS, backtracking, array