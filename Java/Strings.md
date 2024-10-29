## String problems:


## built-in function for strings:
1. str.length()





### 1. length of string:
```
import java.util.*;
public class Main{
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        
    String str=input.nextLine();
        int l=str.length();
        System.out.printf("%d", l);
    }
}
"""
padma is a good girl
20
"""
```

### 2. print character between only one space:
```
import java.util.*;
public class Main{
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        
    String str=input.nextLine();
        int l=str.length();
     for(int i=0; i<l; i++){
         if(i==0){
             System.out.printf("%c", str.charAt(i));
             continue;
         }
         if(str.charAt(i)!=' '){
            System.out.printf(" ");
         System.out.printf("%c", str.charAt(i));
         }
    }
    }
}
"""
padma   is  a    god
p a d m a i s a g o d
"""
```


### 3. print individual characters of a string in reverse order.
```
import java.util.*;
public class Main{
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        
    String str=input.nextLine();
        int l=str.length();
     for(int i=l-1; i>=0; i--){
         if(i==0 && str.charAt(i)!=' '){
            System.out.printf(" ");
             System.out.printf("%c", str.charAt(i));
             continue;
         }
         if(i==l-1){
             System.out.printf("%c", str.charAt(i));
             continue;
         }
         if(str.charAt(i)!=' '){
            System.out.printf(" ");
         System.out.printf("%c", str.charAt(i));
         }
    }
    }
}
"""
padma   is     a   good
d o o g a s i a m d a p
"""
```
