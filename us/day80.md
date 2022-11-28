###question
https://leetcode.com/problems/find-players-with-zero-or-one-losses/submissions/
###Solution
```
class Solution {
    public List<List<Integer>> findWinners(int[][] matches) {
        Set<Integer> winner = new HashSet();
        Map<Integer,Integer> lose = new HashMap();
        for(int [] match: matches) {
            int win = match[0];
            int loser = match[1];
            winner.add(win);
            lose.put(loser, lose.getOrDefault(loser,0) + 1);
        }
        
        List<Integer> l1 = new ArrayList();
        List<Integer> l2 = new ArrayList();
        for(int win: winner) {
            if(!lose.containsKey(win)) l1.add(win);
        }
        
        for(Map.Entry<Integer,Integer> entry: lose.entrySet()) {
            if(entry.getValue() == 1) {
                l2.add(entry.getKey());
            }
        }
        List<List<Integer>> r = new ArrayList();
        Collections.sort(l1);
        Collections.sort(l2);
        r.add(l1);
        r.add(l2);
        return r;
    }
}
```

###Conclustion
Runtime beat 91%
Memory beat 93%

###Related Topic
Array, Hash table