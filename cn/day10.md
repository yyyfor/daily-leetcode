###question
https://leetcode.cn/problems/implement-magic-dictionary/
###Solution
```
class MagicDictionary {
    Map<Integer,List<String>> map;
    public MagicDictionary() {
        map = new HashMap();
    }
    
    public void buildDict(String[] dictionary) {
        for(String s : dictionary) {
            List<String> list = map.getOrDefault(s.length(), new ArrayList());
            list.add(s);
            map.put(s.length(), list);
        }
    }
    
    public boolean search(String searchWord) {
        if(map.get(searchWord.length()) == null) return false;
        List<String> list = map.get(searchWord.length());
        for(int i = 0 ; i < list.size(); i++) {
            int count = 0;
            String s = list.get(i);
            for(int j = 0 ; j < searchWord.length() ; j++) {
                if(s.charAt(j) != searchWord.charAt(j)) {
                    count++;
                    if(count > 1) break;
                }
            }
            if(count == 1) return true;
        }
        return false;

    }
}

/**
 * Your MagicDictionary object will be instantiated and called as such:
 * MagicDictionary obj = new MagicDictionary();
 * obj.buildDict(dictionary);
 * boolean param_2 = obj.search(searchWord);
 */
```

###Conclustion
Runtime beat 88%
Memory beat 79%
使用map存字符串的长度

###Related Topic
Trie, Hash table