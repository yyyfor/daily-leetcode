###question
https://leetcode.cn/problems/replace-words/
###Solution
```
class Solution {
    public String replaceWords(List<String> dictionary, String sentence) {
        Collections.sort(dictionary, (o1 , o2) -> o1.length() - o2.length());
        String [] arrays = sentence.split(" ");
        String result = "";
        for(int i = 0 ; i < arrays.length; i++) {
            String s = arrays[i];
            for(String d: dictionary) {
                if(s.length() < d.length()) continue;
                if(s.substring(0, d.length()).equals(d)) {
                    arrays[i] = d;
                    break;
                }
            }
        }
        for(String s : arrays) {
            result += s + " ";
        }
        return result.trim();

    }
}
```

###Conclustion
Runtime beat 23%
Memory beat 67%
dfs.使用dp数组记录计算过的值

###Related Topic
array,string