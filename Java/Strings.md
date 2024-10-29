## String problems:


## built-in function for strings:
1. str.length()
2. str.trim().replaceAll("\\s+", " ") --> remove leading and trailing spaces in a string
3. Character.isDigit(ch) -- to check a char digit or not
4. Character.isLetter(ch) --> to check a char is alpha or not
5. str1.equals(str2) --> compare two string as equal or not?
6. "aeiou".indexOf(ch)!= -1 ---> char is vowel or else consonant
7. str.toCharArray() -- to convert a string to char array





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

### 7. count the total number of alphabets, digits and special characters in a string.
```
import java.util.*;
public class Main{
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        
        String str=input.nextLine();
        int dc=0, ac=0, sc=0;
        int l=str.length();
        for(int i=0; i<l; i++){
            if(Character.isDigit(str.charAt(i))){
                dc++;
            }
            else if(Character.isLetter(str.charAt(i))){
                ac++;
            }
            else{
                sc++;
            }
        }
        System.out.printf("digits: %d\nalphas: %d\nspl chars: %d", dc, ac, sc);
        input.close();
    }
}
"""
dhsdjkf3443$#$#$##
digits: 4
alphas: 7
spl chars: 7
"""
```

### 8. copy one string to another string. -1
```
import java.util.*;
public class Main{
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        
        String str1=input.nextLine();
        String str2=str1;
        System.out.printf("%s %s", str1, str2);
        input.close();
    }
}
"""
padma //str1
padma padma //str1 str2
"""
```

### 9. count the total number of vowels or consonants in a string.
```
import java.util.*;
public class Main{
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        
        String str=input.nextLine().toLowerCase();
        int l=str.length();
        int vc=0, cc=0;
        for(int i=0; i<l; i++){
            char ch=str.charAt(i);
            
            if(Character.isLetter(ch)){
                if("aeiou".indexOf(ch)!= -1){
                    vc++;
                }
                else{
                    cc++;
                }
            }
        }
        System.out.printf("vowel count: %d\nConsonants count: %d", vc, cc);
        
    }
}
"""
Padmavathi
vowel count: 4
Consonants count: 6
"""
```

### 10. the maximum number of character in a string.
```
import java.util.*;
public class Main{
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        
        String str=input.nextLine().toLowerCase();
        char[] arr=str.toCharArray();
        int l=arr.length;
        int maxCount=0;
        int index=0;
        for(int i=0; i<l; i++){
            int count=1;
            if(arr[i]!=' '){
            for(int j=i+1; j<l; j++){
                if(arr[i]==arr[j]){
                    count++;
                    arr[j]=' ';
                }
            }
            if(count>maxCount){
                maxCount=count;
                index=i;
            }
        }
    }
    System.out.printf("%c", arr[index]);
    }
}
"""
padmavah thi
a
"""
```
