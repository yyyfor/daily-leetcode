###question
https://leetcode.cn/problems/design-an-ordered-stream/
###Solution
```
public class OrderedStream {
    private String[] strings;
    int ptr;

    public OrderedStream(int n) {
        strings = new String[n + 1];
        ptr = 1;
    }

    public List<String> insert(int idKey, String value) {
        strings[idKey] = value;
        List<String> res = new ArrayList<>();
        while (ptr < strings.length && strings[ptr] != null) {
            res.add(strings[ptr++]);
        }
        return res;
    }
}
```

###Conclustion
Runtime beat 85%
Memory beat 38%

###Related Topic
Hash table, Array