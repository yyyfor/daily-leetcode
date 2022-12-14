###question
https://leetcode.cn/problems/replace-words/discussion/
###Solution
```
class Solution {
    public String replaceWords(List<String> dictionary, String sentence) {
        Trie trie = new Trie();
        build(dictionary, trie);
        String [] strs = sentence.split(" ");
        StringBuilder sb = new StringBuilder();
        for(String s: strs) {
            sb.append(find(trie, s));
            sb.append(" ");
        }
        return sb.toString().trim();
    }

    private String find(Trie trie, String s) {
        for(int i = 0 ; i < s.length(); i++) {
            int index = s.charAt(i) - 'a';
            Trie t = trie.array[index];
            if(t == null) return s;
            if(t.val == 1) return s.substring(0, i + 1);
            trie = t;
        }
        return s;
    }

    private void build(List<String> dictionary, Trie trie) {
        for(String d: dictionary) {
            build(d, trie);
        }
    }

    private void build(String d, Trie trie) {
        for(int i = 0 ; i < d.length(); i++) {
            char ch = d.charAt(i);
            int index = ch - 'a';
            if(trie.array == null) {
                trie.array = new Trie[26];
            }
            Trie t = null;
            if(trie.array[index] == null) {
                t = new Trie();
                t.val = (i == d.length() - 1) ? 1 : 0;
                t.ch = ch;
                trie.array[index] = t;
            } else {
                t = trie.array[index];
                if(i == d.length() - 1) {
                    t.val = 1;
                }
            }
            trie = t;   
        }
    }
}

class Trie {
    Trie [] array;
    int val;
    char ch;
}
```


###Conclustion
Runtime beat 100%
Memory beat 19%

###Related Topic
Trie