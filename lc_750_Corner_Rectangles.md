[https://leetcode.com/problems/number-of-corner-rectangles/discuss/110196/short-JAVA-AC-solution-(O(m2-*-n))-with-explanation.](https://leetcode.com/problems/number-of-corner-rectangles/discuss/110196/short-JAVA-AC-solution-(O(m2-*-n))-with-explanation.)

```
class Solution {
    public int countCornerRectangles(int[][] grid) {
        int result = 0;
        for (int row = 0; row < grid.length - 1; row++) {
            for (int row2 = row + 1; row < grid.length; row2++) {
                int counter = 0;
                for (int col = 0; col < grid[0].length; col++) {
                    if (grid[row][col] == 1 && grid[row2][col] == 1) {
                        counter++;
                    }
                }
                if (counter > 0) {
                    result += counter * (counter - 1) / 2;
                }
            }
        }
        return result;
    }
}
```
