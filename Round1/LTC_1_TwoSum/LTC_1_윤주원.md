#  LTC_1_TwoSum 윤주원 [2/17 토요일] </br>
문제 주소: https://leetcode.com/problems/two-sum/description/ </br>
푼 시간 : 35분 </br>
시간 복잡도 : O(n^2)

<접근법>
```
0번부터 끝까지 
1. nums 배열
2. 
```

```java

class Solution {
    public int[] twoSum(int[] nums, int target) {
        int len = nums.length;
        int[] resulf = null;

        // 
        for(int start=0; start < len; start++){
            for(int t=start+1; t < len; t++){
                int r = nums[start] + nums[t];
                if(r == target) {
                    resulf = new int[] {start, t};
                    return resulf;
                }
            }
        }
        return resulf;
    }
}
```
