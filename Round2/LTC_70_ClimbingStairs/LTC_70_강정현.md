# LTC_70_Climbing Stairs [2/22 목요일] </br>
문제 주소: https://leetcode.com/problems/climbing-stairs/description/ </br>
푼 시간: 50분 </br>

<접근법>
```
주어진 계단의 수에 대해 가능한 모든 조합을 계산한 후 그 값을 반환.
```


```java
class Solution {
    public int climbStairs(int n) {
        // 계단을 오르는 방법의 수를 저장할 변수 cnt를 초기화.
        int cnt = 0;
        
        // 0부터 n/2까지 반복하면서 계단을 오르는 방법을 계산.
        for(int i = 0; i <= n/2; i++){
            // i개의 2단계 걸음과 n - i*2개의 1단계 걸음으로 이루어진 경우를 고려.
            int twoStep = i;
            int oneStep = n - i * 2;

            // 전체 방법의 수를 계산하기 위해 분자와 분모를 구한다.
            int numerator = fact(oneStep + twoStep); // 분자
            int denominator = fact(twoStep) * fact(oneStep); // 분모

            // 현재 조합의 경우의 수를 전체 방법의 수에 카운트
            cnt += numerator / denominator;
        }
        return cnt;
    }

    // 팩토리얼 값을 계산하는 메서드
    public int fact(int num) {
        // 재귀 함수로 팩토리얼 값을 계산.
        if (num <= 1) {
            if (num == 0) {
                num = 1; // 0!인 경우
            }
            return num;
        } else {
            return fact(num-1) * num; // 재귀
        }
    }
}
```
