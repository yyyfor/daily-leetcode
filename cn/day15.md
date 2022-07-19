###question
https://leetcode.cn/problems/my-calendar-ii/
###Solution
```
class MyCalendarTwo {
    TreeMap<Integer, Integer> map = new TreeMap<>();

    public boolean book(int start, int end) {
        map.put(start, map.getOrDefault(start, 0) + 1);
        map.put(end, map.getOrDefault(end, 0) - 1);
        int cnt = 0;
        for (int p : map.values()) { // 按时间点进行进行扫描
            cnt += p;
            if (cnt >= 3) {
                map.put(start, map.get(start) - 1);
                map.put(end, map.get(end) + 1);
                return false; // 三重预定
            }
        }
        return true;
    }
}

```

###Conclustion
Runtime beat 32%
Memory beat 68%
使用treeMap，按序从map里取value

###Related Topic
Ordered Set