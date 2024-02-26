# LTC_79_ClimbingStairs 이강욱 [2/23 목요일] </br>
문제 주소: https://leetcode.com/problems/climbing-stairs/submissions/1182198627/ </br>
푼 시간: 18분 </br>
시간 복잡도: O() </br>

<접근법>
```
기본적인 다이나믹 프로그래밍 문제이다. 
점화식을 짜고, 재귀호출로 하는게 아니고 Bottom-Up 형식으로 처리하면 된다.  
```


```java
class Solution {
    public int climbStairs(int n) {
        int[] mem = new int[n+1];
        mem[0] = 1;
        mem[1] = 1;

        for(int i=2; i<=n; i++){
            mem[i] = mem[i-1] + mem[i-2];
        }
        return mem[n];
    }
}
```
