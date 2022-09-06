###question
https://leetcode.cn/problems/count-unique-characters-of-all-substrings-of-a-given-string/submissions/
###Solution
```
class Solution {
    public int uniqueLetterString(String s) {
        int length = s.length();
        Map<Character, List<Integer>> map = new HashMap();
        for(int i = 0 ; i < length; i++) {
            char ch = s.charAt(i);
            List<Integer> list = map.getOrDefault(ch, new ArrayList<Integer>());
            list.add(i);
            map.put(ch, list);
        }

        int result = 0;
        for(Map.Entry<Character, List<Integer>> entry: map.entrySet()) {
            List<Integer> list = entry.getValue();
            if(list.size() == 1) {
                System.out.println(list.get(0));
                result += (length - list.get(0)) * (list.get(0) + 1);
                continue;
            }
            list.add(0, -1);
            list.add(length);
            for(int i = 1 ; i < list.size() - 1; i++) {
                result += (list.get(i) - list.get(i - 1)) * (list.get(i + 1) - list.get(i)); 
            }
        }
        return result;
    }
}
```

###Conclustion
Runtime beat 17%
Memory beat 35%

###Related Topic
Hash Table