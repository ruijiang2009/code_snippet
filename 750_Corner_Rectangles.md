[https://leetcode.com/problems/network-delay-time/discuss/210698/Java-Djikstrabfs-Concise-and-very-easy-to-understand](https://leetcode.com/problems/network-delay-time/discuss/210698/Java-Djikstrabfs-Concise-and-very-easy-to-understand)

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
