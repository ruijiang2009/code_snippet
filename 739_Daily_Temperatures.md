
```
class Solution {
    public int[] dailyTemperatures(int[] temperatures) {
        int len = temperatures.length;
        int[] result = new int[len];
        Stack<Integer> stack = new Stack<Integer>();

        for(int i = 0; i < len; i++) {
            while(!stack.isEmpty() && temperatures[i] > temperatures[stack.peek()]) {
                int idx = stack.peek();
                stack.pop();
                result[idx] = i - idx;
            }
        }

        return result;
    }
}
```
