#  LTC_20_Valid Parentheses 이강욱 [2/18 일요일] </br>
문제 주소: https://leetcode.com/problems/valid-parentheses/ </br>
푼 시간: 48분

<접근법>
```
그냥 stack 사용해서 짝 맞추면 된다. 
여는 괄호일때는 push 시키고, 닫는 괄호면 peek 해서 짝이 맞으면 pop 시킨다. 
주의할점은, 스택에 아무것도 없을 때 닫는괄호가 나오는 경우이다. 
그를 대비하여 닫는 괄호일때 스택이 비어있는지 확인해야한다. 
```


```java
//코드 추가
class Solution {
    public boolean isValid(String s) {
        Stack<Character> st = new Stack<>(); //stack 선언

        for (int i=0; i<s.length(); i++){
            /*
             *switch 문으로 케이스 나눔
             *여는 괄호일때는 그냥 push,
             *닫는 괄호일때는 peek 해서 쌍이 맞는지 비교,
             *맞으면 pop, 다르면 false 리턴
             */
            switch (s.charAt(i)) {
                case '(':
                    st.push('(');
                    break;

                case '{':
                    st.push('{');
                    break;

                case '[':
                    st.push('[');
                    break;

                case ')':
                    if(!st.isEmpty()&&(Character.compare(st.peek(), '('))==0){ //char 비교는 Charcater.compare 사용
                        st.pop();
                    }
                    else{
                        return false;
                    }
                    break;

                case '}':
                    if(!st.isEmpty()&&(Character.compare(st.peek(), '{'))==0){
                        st.pop();
                    }
                    else{
                        return false;
                    }
                    break;

                case ']':
                    if(!st.isEmpty()&&(Character.compare(st.peek(), '['))==0){
                        st.pop();
                    }
                    else{
                        return false;
                    }
                    break;


            }

        }
        //스택이 비었으면 true 리턴, 아니면 짝이 안맞은것이므로 false
        return st.isEmpty();
    }
}
```
