#  LTC_1_TwoSum 이강욱 [2/17 토요일] </br>
문제 주소: https://leetcode.com/problems/two-sum/description/ </br>
푼 시간: 1시간 생각 후 힌트 본 뒤 알고리즘 사용법 등 검색하며 30분 코드 작성  </br>

<접근법>
```
물론 하나하나 해도 좋지만 시간 복잡도가 O(n^2) 이므로 너무 과하다. 
hashmap 을 이용하여 O(n) 까지 줄일 수 있다.

원래는 x + y = target 이지만, 한번 바꾸어 생각해서 y = target - x 라고 생각하고,
배열의 앞에서부터 y 가 hash 에 없다면 put 하면서 containsKey 가 만족할때까지 배열을 돌면 해결된다. 

```


```java
//코드 추가
class Solution {
    public int[] twoSum(int[] nums, int target) {
        HashMap<Integer,Integer> map = new HashMap<Integer, Integer>(); //HashMap 선언
        int[] answer = {0,0}; // 정답을 저장할 배열 선언

        for(int i=0; i<nums.length; i++){
            int search = target - nums[i]; // y = target - x 개념을 이용

            /*
             *hashmap 에 search 가 있다면 리턴
             *없다면 hash에 키와 값 추가
             */

            if(!map.containsKey(search)){
                map.put(nums[i],i);
            }
            else {
                answer[0] = map.get(search);
                answer[1] = i;
            }
        }
        return answer;
    }
}
```
