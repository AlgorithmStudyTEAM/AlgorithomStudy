# LTC_62_윤주원 [2/27] </br>
문제 주소: https://leetcode.com/problems/unique-paths/description/?source=submission-noac </br>
푼 시간: 28분 </br>
시간 복잡도: O(n) </br>


<접근법>
```
dp문제이다. 점화식을 짜야한다. d[m][n] = d[m-1][n] + d[m][n-1] 이대로 쭉 가면 나온다. 
bottom-up 형식으로 하나씩 채워서 리턴시켜주었다. 
```


```java
class Solution {
    public int uniquePaths(int m, int n) {
        int[][] d = new int[m][n];
        /**
         일단 맨 윗줄과 맨 왼쪽줄은 일자로 가는 방법 하나밖에 없으므로 1로 채워준다.
         */
        for(int i=0; i<m; i++){
            d[i][0] = 1;
        }
        for(int i=0; i<n; i++){
            d[0][i] = 1;
        }
        /**
         bottom-up 형식으로 차례차례 넣어준다. 
         한 블럭을 기준으로, 왼쪽에서 오는 경우, 위에서 오는 경우 두 가지 경우가 존재한다
         그 두 가지 경우를 더하면 해당 블럭의 경우의 수가 나온다.
         */
        for(int i=1; i<m; i++){
            for(int j=1; j<n; j++){
                d[i][j] = d[i-1][j] + d[i][j-1];
            }
        }
        return d[m-1][n-1];
    }
}
```
