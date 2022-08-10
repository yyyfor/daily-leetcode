###question
https://leetcode.cn/problems/solve-the-equation/submissions/
###Solution
```
class Solution {
    // 简易状态机
    public String solveEquation(String equation) {
        char[] cs = equation.toCharArray();
        // 记录所有x的和
        int xCount = 0;
        // 记录所有数字的和
        int total = 0;
        // 是否等号左边
        boolean isLeft = true;
        for (int i = 0; i < cs.length; i++) {
            char c = cs[i];
            // 默认加法
            boolean add = true;
            int val = 0;
            switch (c) {
                case '=':
                    isLeft = false;
                    // 由于需要将等号左边数字的和移动到等号右边，所以需要取反
                    total = -total;
                    break;
                case 'x':
                    val = 1;
                case '0':
                case '1':
                case '2':
                case '3':
                case '4':
                case '5':
                case '6':
                case '7':
                case '8':
                case '9':
                    if (i - 1 >= 0 && cs[i - 1] == '-') add = false;
                    while (i < cs.length && cs[i] >= '0' && cs[i] <= '9') {
                        val = val * 10 + cs[i] - '0';
                        i++;
                    }
                    // 根据符号，进行取反操作
                    if (!add) val = -val;
                    if (isLeft) {
                        if (cs[i] == 'x') {
                            xCount += val;
                        } else {
                            total += val;
                        }
                    } else {
                        if (i < cs.length && cs[i] == 'x') {
                            // 在等号右边时，将x移到等号左边，所以要进行取返操作
                            xCount += -val;
                        } else {
                            total += val;
                        }
                    }
                    if (i < cs.length && cs[i] == '=') {
                        isLeft = false;
                        // 由于需要将左边的和移动到右边，所以需要取反
                        total = -total;
                    }
                    break;

            }
        }
        if (xCount != 0) {
            return "x" + "=" + (total / xCount);
        } else if (total == 0) {
            return "Infinite solutions";
        } else {
            return "No solution";
        }
    }
}
```

###Conclustion
Runtime beat 85%
Memory beat 87%

weird test case

###Related Topic
String, Math