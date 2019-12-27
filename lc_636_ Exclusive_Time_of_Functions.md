[https://leetcode.com/problems/exclusive-time-of-functions/discuss/105062/Java-Stack-Solution-O(n)-Time-O(n)-Space](https://leetcode.com/problems/exclusive-time-of-functions/discuss/105062/Java-Stack-Solution-O(n)-Time-O(n)-Space)
```
public int[] exclusiveTime(int n, List<String> logs) {
  int[] res = new int[n];
  Stack<Integer> stack = new Stack<>();
  int prevTime = 0;

  for (String log : logs) {
    String[] parts = log.split(":");
    int taskId = Integer.parseInt([parts[0])
    int curTime = Integer.parseInt(parts[2]);

    if (!stack.isEmpty()) {
      res[stack.peek()] += curTime - prevTime; 
    }

    prevTime = curTime;

    if (parts[1].equals("start")) {
      stack.push(taskId);
    }  else {
      res[stack.pop()]++;
      prevTime++;
    }
  }

  return res;
}
```
