#  LTC_1_TwoSum 윤주원 [2/19 월요일] </br>
문제 주소: https://leetcode.com/problems/valid-parentheses/ </br>
푼 시간 : 43분 </br>
시간 복잡도 : O(n)

<접근법>
```

```

```java

import java.util.*;

class Solution {
    public boolean isValid(String s) {
        char[] chars = s.toCharArray();
        Stack<Character> stackChar = new Stack<>();
        int len = chars.length;

        if((len%2) == 1) return false;

        for(int idx = 0; idx < len; idx++){
            // (,{,[ 일 경우 
            if(chars[idx]=='('||chars[idx]=='{'||chars[idx]=='['){
                stackChar.push(chars[idx]);
            }else{
                char c;
                try{
                    c = stackChar.pop();
                    if(!((chars[idx]-c)==2||(chars[idx]-c)==1)){
                        return false;
                    }
                }catch (Exception e){
                    return false;
                }
            }
        }

        if(!stackChar.isEmpty()) return false;

        return true;
    }
}
```
