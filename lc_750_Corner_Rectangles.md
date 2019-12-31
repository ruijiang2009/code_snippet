[https://leetcode.com/problems/number-of-corner-rectangles/discuss/110196/short-JAVA-AC-solution-(O(m2-*-n))-with-explanation.](https://leetcode.com/problems/number-of-corner-rectangles/discuss/110196/short-JAVA-AC-solution-(O(m2-*-n))-with-explanation.)

```
class Solution {
    public int countCornerRectangles(int[][] grid) {
        int result = 0;
        for (int row = 0; row < grid.length - 1; row++) {
            for (int col = row + 1; col < grid.length; col++) {
                int counter = 0;
                for (int k = 0; k < grid[0].length; k++) {
                    if (grid[row][k] == 1 && grid[col][k] == 1) {
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
