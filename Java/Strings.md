## String problems:


## built-in function for strings:
1. str.length()
2. str.trim().replaceAll("\\s+", " ") --> remove leading and trailing spaces in a string





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

### 4. remove leading and trailing spaces in a string
```
import java.util.*;
public class Main{
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        
    String str=input.nextLine();
        System.out.println(str.trim().replaceAll("\\s+", " "));
        input.close();
    }
}
"""
padma    is   a    good
padma is a good
"""
```

### 5. count the total number of words in a string:
```
import java.util.*;
public class Main{
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        
        String str=input.nextLine();
        String[] words=str.trim().split("\\s+");
        int wordCount=words.length;
        
        System.out.printf("%d", wordCount);
        input.close();
    }
}
"""
padma   is   a   good
4
"""
```

### 6. compare two strings
```
import java.util.*;
public class Main{
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        
        String str1=input.nextLine();
        String str2=input.nextLine();
        boolean result=str1.equals(str2);
        System.out.printf("%s", result);
        input.close();
    }
}
"""
padma
kavi
false
"""
```
