#  LTC_20_ValidParentheses 최지혜 [2/19 월요일] </br>
문제 주소: https://leetcode.com/problems/valid-parentheses </br>
푼 시간: 50분 </br>

<접근법>
```
stack을 만들고 앞 괄호를 조건문으로 걸어둔 후, 앞 괄호가 있으면 stack에 넣어주고 이후에 짝인 뒷 괄호가 나오면
pop이 되게끔 접근했음
```


```java
class Solution {
    public boolean isValid(String s) {
        int len = s.length();

        // input이 홀수면 어차피 false이기 때문에
        if(len % 2 != 0) {
            return false;
        }

        Stack<Character> stack = new Stack<>();

        for(int i=0; i<len; i++){
            char a = s.charAt(i); // input 하나씩 쪼개기

            // 앞 괄호가 input에 있으면 stack에 넣기
            if(a == '(' || a == '{' || a == '['){
                stack.push(a);
            }
            // size가 0이면 괄호가 순서대로 나오지 않았다는 이야기라 false
            else if (stack.size() == 0){
                return false;
            }
            // 짝을 찾아준 다음에 pop 시키기
            else if (a == ')'){
                if(stack.pop() != '('){
                    return false;
                }
            }
            else if (a == '}'){
                if(stack.pop() != '{'){
                    return false;
                }
            }
            else if (a == ']'){
                if(stack.pop() != '['){
                    return false;
                }
            }

        }
        // 올바르게 짝과 순서가 구성돼있으면 stack에 아무것도 남아있으면 안 되기 때문
        return stack.size() == 0;

    }
}

```
