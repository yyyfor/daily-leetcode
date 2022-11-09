###question
https://leetcode.com/problems/online-stock-span/
###Solution
```
class StockSpanner {

    Stack<int []> stack;
    
    public StockSpanner() {
        stack = new Stack();
    }
    
    public int next(int price) {
        int num = 1;
        while(!stack.isEmpty() && price >= stack.peek()[0]) {
            num += stack.pop()[1];
        }
        stack.push(new int [] {price, num});
        return num;
    }
}

/**
 * Your StockSpanner object will be instantiated and called as such:
 * StockSpanner obj = new StockSpanner();
 * int param_1 = obj.next(price);
 */
```

###Conclustion
Runtime beat 96%
Memory beat 98%

###Related Topic
Stack