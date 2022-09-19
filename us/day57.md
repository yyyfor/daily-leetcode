###question
https://leetcode.com/problems/find-duplicate-file-in-system/submissions/
###Solution
```
class Solution {
    public List<List<String>> findDuplicate(String[] paths) {
        Map<String,List<String>> map = new HashMap();
        for(String path: paths) {
            helper(path, map);
        }
        List<List<String>> r = new ArrayList();
        for(Map.Entry<String,List<String>> entry: map.entrySet()) {
            if(entry.getValue().size() > 1) {
                r.add(entry.getValue());
            }
        }
        return r;
    }
    
    private void helper(String path, Map<String,List<String>> map) {
        String [] strs = path.split(" ");
        for(int i = 1; i < strs.length; i++) {
            String str = strs[i];
            String [] ss = content(str);
            List<String> list = map.getOrDefault(ss[1], new ArrayList<String>());
            map.put(ss[1],list);
            list.add(strs[0] + "/" + ss[0]);
        }
    }
    
    private String [] content(String str) {
        String s1 = "";
        String s2 = "";
        int i = 0;
        for(; i < str.length(); i++) {
            if(str.charAt(i) != '(') s1 += str.charAt(i);
            else break;
        }
        s2 = str.substring(i + 1, str.length() - 1);
        return new String [] {s1, s2};
    }
}
```

###Conclustion
Runtime beat 61%
Memory beat 91%

###Related Topic
Array, Hash Table