#  LTC_20_valid-parentheses 강정현 [2/18 일요일] </br>
문제 주소: https://leetcode.com/problems/valid-parentheses/ </br>
푼 시간: 10 min </br>

<접근법>
```
열린 괄호 뒤에 바로 닫는 괄호가 나오기 때문에 stack을 이용할 필요가 없기 때문에 다음과 같이 단순하게
if 문으로 특정 괄호가 나오면 조건에 맞는 괄호가 나왔을 경우 참이 되도록 작성함.
```


```java
class Solution {
    public boolean isValid(String s) {
        for (int i = 0; i < s.length(); i++) {
            if (s.charAt(i) =='(') {
                if (s.charAt(i+1) == ')') {
                    continue;
                } else {
                    return false;
                }
            } else if (s.charAt(i) =='[') {
                if (s.charAt(i+1) == ']') {
                    continue;
                } else {
                    return false;
                }
            } else if (s.charAt(i) =='{') {
                if (s.charAt(i+1) == '}') {
                    continue;
                } else {
                    return false;
                }
            } else {
                continue;
            }
        }
        return true;
    }
}
```
