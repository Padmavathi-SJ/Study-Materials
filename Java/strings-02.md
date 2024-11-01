### methods:

### missed problmes nums: 2
### 1. Get the character at the given index within the string.
```
import java.util.*;
public class Main {
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);

        String str=input.nextLine();
        int index=input.nextInt();
        for(int i=0; i<str.length(); i++){
            if(i==index){
                System.out.println(str.charAt(i));
            }
        }
    }
}
"""
Java Exercises!
10
i
"""
```

### 2. get the character (Unicode code point) at the given index within the string.
```
import java.util.*;
public class Main {
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);

        String str=input.nextLine();
        int index=input.nextInt();
        int value=str.codePointAt(index);
        System.out.println(value);
    }
}
"""
Hello, World!
7
87
"""
```

### 3. get the character (Unicode code point) before the specified index within the string.
```
import java.util.*;
public class Main {
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);

        String str=input.nextLine();
        int index=input.nextInt();
        int value=str.codePointBefore(index);
        System.out.println(value);
    }
}
"""
w3resource.com
1
119
"""
```

### 4. count Unicode code points in the specified text range of a string.
```
import java.util.*;
public class Main {
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);

        String str=input.nextLine();
        int start=input.nextInt();
        int end=input.nextInt();
        int value=str.codePointCount(start, end);
        System.out.println(value);
    }
}
"""
w3resource.com
1
10
9
"""
```

### 5. compare two strings lexicographically.
```
import java.util.*;
public class Main {
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);

        String str1=input.nextLine();
        String str2=input.nextLine();
        if(str1.compareTo(str2) == 0){
            System.out.println("equal");
        }
        else if(str1.compareTo(str2) > 0){
            System.out.println("str1 is greater than str2");
        }
        else{
            System.out.println("str1 is lesser than str2");
        }
        
    }
}
"""
This is Exercise 1
This is Exercise 2
str1 is lesser than str2
"""
```

### 6. compare two strings lexicographically, ignoring case differences.
```
import java.util.*;
public class Main {
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);

        String str1=input.nextLine();
        String str2=input.nextLine();
        if(str1.equalsIgnoreCase(str2)){
            System.out.println("equal");
        }
        else if(str1.compareTo(str2) > 0){
            System.out.println("str1 is greater than str2");
        }
        else{
            System.out.println("str1 is lesser than str2");
        }
        
    }
}
"""  
This is exercise 1
This is Exercise 1
equal
"""
```
