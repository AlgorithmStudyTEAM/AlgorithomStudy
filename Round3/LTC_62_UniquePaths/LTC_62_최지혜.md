#  LTC_62_Unique Paths 최지혜 [02/29 목요일] </br>
문제 주소: https://leetcode.com/problems/unique-paths/ </br>
푼 시간: 50분 </br>

<접근법>
```
for문으로 현 위치의 왼쪽의 누적값과 위의 누적값을 더한 값으로 저장한다.
```


```java
class Solution {
    public int uniquePaths(int m, int n) {
        int[][] arr = new int[m][n];

        for(int i=0; i<m; i++){ // 각 첫번째 행 1로 초기화
            arr[i][0] = 1;
        }

        for (int i = 0; i < n; i++) {// 각 첫번째 열 1로 초기화
            arr[0][i] = 1;
        }

        for (int i = 1; i < n; i++) {
            for (int j = 1; j < m; j++) {
                arr[j][i] = arr[j - 1][i] + arr[j][i - 1];//현 위치 누적값 = 이전 행 누적값 + 이전 열 누적값
            }
        }

        return arr[m - 1][n - 1];
    }
}

```