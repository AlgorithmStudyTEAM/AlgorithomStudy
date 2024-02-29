# LTC_62_윤주원 [2/28] </br>
문제 주소: https://leetcode.com/problems/unique-paths/description/?source=submission-noac </br>
푼 시간: 35분 </br>
시간 복잡도: O(n) </br>


<접근법>
```
처음에는 콤비네이션으로 문제를 풀려고 했다. 하지만 펙토리얼 때문에 값이 너무 커져서 
정상적으로 값이 저장되지 않았다.
// 1 1 1 1 1 1
// 1 2 3 4 5 6 
// 1 3 6 10 15 21 
// 1 4 10 20 35 56 
위와깉은 형태로 풀게 되면 팩토리얼도 안쓰고 O(n)밖에 안걸린다는 알고 문제를 풀었다.
```


```java
class Solution {

    // 1 1 1 1 1 1
    // 1 2 3 4 5 6 
    // 1 3 6 10 15 21 
    // 1 4 10 20 35 56 

    public int uniquePaths(int m, int n) {
        int[][] p = new int[m][n];

        for(int y=0; y<m; y++){
            for(int x=0; x<n; x++){
                if(x==0||y==0){
                    p[y][x] = 1;
                }else{
                    p[y][x] = p[y-1][x] + p[y][x-1];
                }
            }
        }

        return p[m-1][n-1];
    }

    /*
    // 콘비네이션으로 풀려고 했는데
    // 팩토리얼이 너무 커져서 안됨
    int[] p;

    int dp(int num){
        if(num==1){
            return p[1];
        }
        else if(p[num] != 0) {
            return p[num];
        }else{
            int result = num * dp(num-1);
            p[num] = result;
            System.out.println(p[num]);
            return result;
        }
    }

    public int uniquePaths(int m, int n) {
        p = new int[(m+n-1)];
        p[1] = 1;
        int result = dp(m+n-2)/(dp(m-1)*dp(n-1));
        return result;
    }
    */
}
```
