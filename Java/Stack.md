## Stack Data Structure
### Problems solved using stack data structure

### Valid parantheses
```
import java.util.*;
class Main{
private static boolean isMatching(char open, char close){
    return (open == '{' && close=='}') ||
           (open == '[' && close==']') ||
           (open == '(' && close==')');
}
private static boolean isValid(String str){
    Stack<Character> stack=new Stack<>();
    for(char ch:str.toCharArray()){
        if(ch=='{' || ch=='(' || ch=='['){
            stack.push(ch);
        }
        else if(stack.isEmpty() || !isMatching(stack.pop(), ch)){
            return false;
        }
    }
    return stack.isEmpty();
}
public static void main(String[] args){
        String str="([{[()]}])";
        
        if(isValid(str)){
            System.out.println("valid");
        }
        else{
            System.out.println("not valid");
        }
        
    }
}
"""
Valid
"""
```
