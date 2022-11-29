###question
https://leetcode.com/problems/insert-delete-getrandom-o1/
###Solution
```
class RandomizedSet {
    Map<Integer,Integer> map;
    List<Integer> list;
    Random random;
    int size;
    public RandomizedSet() {
        map = new HashMap();
        list = new ArrayList();
        random = new Random();
        size = 0;
    }
    
    public boolean insert(int val) {
        if(map.containsKey(val)) return false;
        map.put(val, size);
        list.add(val);
        size++;
        return true;
    }
    
    public boolean remove(int val) {
        if(!map.containsKey(val)) return false;
        int index = map.get(val);
        if(index < size) {
            for(int i = index + 1; i < size; i++) {
                int num = list.get(i);
                int cur = map.get(num);
                map.put(num, cur - 1);
            }
        }
        map.remove(val);
        list.remove(index);
        size--;
        return true;
    }
    
    public int getRandom() {
        int index = random.nextInt(size);
        return list.get(index);
    }
}

/**
 * Your RandomizedSet object will be instantiated and called as such:
 * RandomizedSet obj = new RandomizedSet();
 * boolean param_1 = obj.insert(val);
 * boolean param_2 = obj.remove(val);
 * int param_3 = obj.getRandom();
 */
```

swap element when delete

###Conclustion
Runtime beat 5%
Memory beat 5%

###Related Topic
String