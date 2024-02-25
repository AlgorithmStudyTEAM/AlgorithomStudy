#  LTC_70_Climbing Stairs [2/22] </br>
문제 주소: https://leetcode.com/problems/climbing-stairs/description </br>
푼 시간: 30분 </br>
시간 복잡도: O(n) </br>

<접근법>
```
처음에는 1,2,3,5,8.... 뒤에 두값을 더한 값이 결과가 나와야해서 재귀를 이용했다.
하지만 수가 커지면서 작업하는 시간이 기학급수적으로 늘어나 시간초과가 되었다.
생각해보니 같은 숫자를 여러번 재귀를 통해서 중복해서 값을 내는 것을 보고 한번만 값을 구하면 그걸 사용하는 방식으로 업데이트
그래서 한번 결과를 낸 값을 array에 저장하여는 식으로 업데이트를 시켰다.
```


```java
class Solution {

    int result(int[] levels, int n){
        // 기본적으로 levels[n]에 값을 보낸다.
        // 만약 n위치에 값이 0이면 재귀적으로 값을 구함
        if(levels[n] == 0) {
            levels[n] = result(levels, n-1) + result(levels, n-2);
        }
        
        return levels[n];
    }

    public int climbStairs(int n) {
        // 각 번호에 값을 저장해서 사용한다.
        int[] levels = new int[46];
        // 1, 2번 값을 저장한다.
        levels[1] = 1;
        levels[2] = 2;
        // 재귀함수 시작
        return result(levels, n);

        // TIME LIMIT
        /*
        if(n==1){
            return 1;
        }else if(n==2){
            return 2;
        }

        return climbStairs(n-1) + climbStairs(n-2);
        */
    }


}
```
