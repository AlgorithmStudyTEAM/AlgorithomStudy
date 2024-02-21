#  LTC_1_TwoSum 최지혜 [2/18 일요일] </br>
문제 주소: https://leetcode.com/problems/two-sum/description/ </br>
푼 시간: 40분 </br>

<접근법>
```
for문으로 배열 돌면서 if문으로 두 수의 합이 target인 경우 정답 배열
```


```java
class Solution {
    public int[] twoSum(int[] nums, int target) {
        for(int i=0; i<nums.length; i++){
            for(int j=i+1; j<nums.length; j++ ){
                if(nums[i] + nums[j]==target){
                    return new int[]{i,j};
                }
            }
        }
        return new int[]{};
    }
}

```
