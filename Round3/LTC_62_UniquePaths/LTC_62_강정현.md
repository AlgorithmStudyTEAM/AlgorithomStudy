# LTC_62_강정현 [2/28] </br>
문제 주소: https://leetcode.com/problems/unique-paths/description/?source=submission-noac </br>
푼 시간: 10분 </br>
시간 복잡도: O(n) </br>


<접근법>
```
가로 세로로 첫번째 줄에 해당하는 값은 1로 지정. 그리고 만나는 지점끼리 더한다. 그렇게 finish 지점까지 수행한다.
```


```java
class Solution {
    public int uniquePaths(int m, int n) {

        int[][] grid = new int[m][n];

        for(int i = 0; i < grid[0].length; i++) {
            grid[0][i] = 1;
        }

        for(int i = 0; i < grid.length; i++) {
            grid[i][0] = 1;
        }

        for(int i = 1; i < grid.length; i++) {
            for(int j = 1; j < grid[0].length; j++) {
                grid[i][j] = grid[i-1][j] + grid[i][j-1];
            }
        }

        return grid[m-1][n-1];
    }
}
```
