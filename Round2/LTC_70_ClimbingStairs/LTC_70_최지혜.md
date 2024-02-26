#  LTC_70_Climbing Stairs 최지혜 [02/26 월요일] </br>
문제 주소: https://leetcode.com/problems/climbing-stairs/ </br>
푼 시간: 30분 </br>

<접근법>
```
예를 들어 3번째 값이면 arr[3] = arr[1] + arr[2] 이렇게 앞에 두 값을 더한 점화식이라서 
점화식을 푸는 방식으로 접근했다.
```


```java
class Solution {
    public int climbStairs(int n) {
        if(n == 1){ // 계단 한 개일 때
            return 1;
        }
        else if (n == 2){
            return 2;
        }

        int[] arr = new int[n];
        arr[0] = 1;
        arr[1] = 2;

        for(int i=2; i<n; i++){ // 점화식
            arr[i] = arr[i-2] + arr[i-1];
        }

        return arr[n-1]; // 배열의 마지막 값 반환
    }
}

```
