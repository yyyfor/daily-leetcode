###question
https://leetcode.cn/problems/encode-and-decode-tinyurl/
###Solution
```
public class Codec {

    Map<String, String> map = new HashMap();
    int count = 0;
    // Encodes a URL to a shortened URL.
    public String encode(String longUrl) {
        String str = String.valueOf(count);
        map.put(str, longUrl);
        count++;
        return str;
    }

    // Decodes a shortened URL to its original URL.
    public String decode(String shortUrl) {
        return map.get(shortUrl);
    }
}

// Your Codec object will be instantiated and called as such:
// Codec codec = new Codec();
// codec.decode(codec.encode(url));
```

###Conclustion
Runtime beat 79%
Memory beat 49%
使用自增整数技术，实际开发中不可行。需要进行编码和去重

###Related Topic
String, Hash Table, Hash