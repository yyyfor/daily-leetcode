###question
https://leetcode.cn/problems/validate-stack-sequences/
###Solution
```
class Solution {
    public boolean validateStackSequences(int[] pushed, int[] popped) {
        Stack<Integer> stack = new Stack();
        int index = 0;
        for(int i = 0 ; i < pushed.length; i++) {
            stack.push(pushed[i]);
            index = check(stack, popped, index);
        }

        return stack.isEmpty();
    }

    private int check(Stack<Integer> stack, int [] popped, int index) {
        while(!stack.isEmpty()) {
            if(stack.peek() == popped[index]) {
                stack.pop();
                index++;
            } else return index;
        }
        return index;
    }
}
```

###Conclustion
Runtime beat 58%
Memory beat 42%

###Related Topic
Stack, Array