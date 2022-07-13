###question
https://leetcode.cn/problems/asteroid-collision/
###Solution
```
class Solution {
    public int[] asteroidCollision(int[] asteroids) {
        Stack<Integer> stack = new Stack();
        stack.push(asteroids[0]);
        boolean add = true;
        for(int i = 1; i < asteroids.length; i++) {
            while(!stack.isEmpty()) {
                if(stack.peek() < 0) {
                    stack.push(asteroids[i]);
                    break;
                }
                if(asteroids[i] > 0) {
                    stack.push(asteroids[i]);
                    break;
                } 
                if(stack.peek() == -1 * asteroids[i]) {
                    add = false;
                    stack.pop();
                    break;
                } else if(stack.peek() > -1 * asteroids[i]){
                    add = false;
                    break;
                } else {
                    stack.pop();
                }
            }
            if(stack.isEmpty() && add) {
                stack.push(asteroids[i]);
            }
            add = true;
        }
        int [] r = new int [stack.size()];
        for(int i = stack.size() - 1; i >= 0; i--) {
            r[i] = stack.pop();
        }
        return r;
        
    }
}
```

###Conclustion
Runtime beat 16%
Memory beat 8%
使用stack

###Related Topic
Array, stack