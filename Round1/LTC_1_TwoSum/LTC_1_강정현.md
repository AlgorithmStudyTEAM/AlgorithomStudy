#  LTC_1_TwoSum 강정현 [2/17 토요일] </br>
문제 주소: https://leetcode.com/problems/two-sum/description/ </br>
푼 시간: 16 min </br>

<접근법>
```
이중 for문을 통한 배열 접근.
```


```java
class Solution {
    public int[] twoSum(int[] nums, int target) {
        int[] output = new int[2];
        int sum;
        for (int i = 0; i < nums.length; i++) {
            sum = nums[i];
            for(int j = i + 1; j < nums.length; j++) {
                if(target == sum + nums[j]) {
                    output[0] = i;
                    output[1] = j;
                    return output;
                }
            }
        }
        return null;
    }
}
```
