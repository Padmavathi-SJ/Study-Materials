## String problems:

1. input.nextLine() ---> it will read entire line as a sigle input
2. 



## built-in function for strings:
1. str.length()
2. str.trim().replaceAll("\\s+", " ") --> remove leading and trailing spaces in a string
3. Character.isDigit(ch) -- to check a char digit or not
4. Character.isLetter(ch) --> to check a char is alpha or not
5. str1.equals(str2) --> compare two string as equal or not?
6. "aeiou".indexOf(ch)!= -1 ---> char is vowel or else consonant
7. str.toCharArray() -- to convert a string to char array
8. str1.compareTo(str2) --> to compare two strings to find str1 is greater or lesser than str2
9. Character.isLowerCase(ch){ --- }
10. Character.isUpperCase(ch){ --- }
11. ch=Character.toLowerCase(ch);
12. ch=Character.toUpperCase(ch);
13. ch1==ch2 --> to compare two characters
14. str1 + " " + str2 ---> to combine two strings
15. Arrays.sort(words, Comparator.comparingInt(String::length)); --> sort as array of strings





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

### 11. Reverse the words in a string array:
```
import java.util.*;
public class Main{
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        
        int n=input.nextInt();
        String[] arr=new String[n];
        for(int i=0; i<n; i++){
            arr[i]=input.next();
        }
        
        Arrays.sort(arr, Collections.reverseOrder());
        
        for(int i=0; i<n; i++){
            System.out.printf("%s ", arr[i]);
        }
        input.close();
    }
}
"""
5
Hi padma how are you
you padma how are Hi
"""
```

### 12. program to sort a string array in ascending order.
```
import java.util.*;

public class string {
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);

        String str=input.nextLine();
        char[] letters=new char[str.length()];
        letters=str.toCharArray();
        Arrays.sort(letters);
        for(int i=0; i<letters.length; i++){
            if(letters[i]!=' '){
            System.out.printf("%c", letters[i]);
        }
    }
    }
}
"""
hi padm ahow are you
aaadehhimoopruwy
"""
```

### 13.read a string from the keyboard and sort it using bubble sort.
```
import java.util.*;

public class string {
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);

       int n=input.nextInt(); 
    String[] words=new String[n];
    for(int i=0; i<n; i++){
        words[i]=input.next().toLowerCase();
    }

    for(int i=0; i<n-1; i++){
        for(int j=0; j<n-i-1; j++){
            if(words[j].compareTo(words[j+1]) > 0){
                String temp=words[j];
                words[j]=words[j+1];
                words[j+1]=temp;
            }
        }
    }
    for(int i=0; i<n; i++){
        System.out.println(words[i]);
    }
    }
}
"""
3
zero
two
one

one
two
zero
"""
```

### 14. extract a substring from a given string.
```
import java.util.*;

public class string {
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);

    String str=input.nextLine();
    int pos=input.nextInt();
    int len=input.nextInt();
    char[] arr=new char[str.length()];
    arr=str.toCharArray();
    char[] result=new char[len];
    int index=0, limit=0;
    for(int i=pos-1; i<arr.length; i++){
        result[index++]=arr[i];
        limit++;
        if(limit==len){
            break;
        }
    }
    for(int i=0; i<index; i++){
        System.out.printf("%c", result[i]);
    }
    }
}

"""
this is test string
14
6
string
"""
```

### 15. check whether a substring is present in a string.
```
import java.util.*;

public class string {
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);

    String str=input.nextLine();
    String search=input.nextLine();
    boolean result=str.contains(search);
    if(result){
        System.out.println("The substring is exists in the string");
    }
    else{
        System.out.println("The substring is not exists in the string");
    }
    }
}
"""
this is a test string
test
The substring is exists in the string
"""
```

### 16.  find the number of times a given word 'the' appears in the given string.
```
import java.util.*;

public class string {
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);

    String[] words=input.nextLine().split(" ");
    String search=input.nextLine();
    int count=0;
    for(int i=0; i<words.length; i++){
        if(words[i].equals(search)){ //if(words[i].compareTo(search))
            count++;
        }
    }
    System.out.println(count);
    }
}

"""
this is the is the is string
is
3
"""
```

### 17. read a sentence and replace lowercase characters with uppercase and vice versa.
```
import java.util.*;

public class string {
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);

    String str=input.nextLine();
    char[] result=new char[str.length()];
    result=str.toCharArray();
    for(int i=0; i<result.length; i++){
        char ch=result[i];
        if(Character.isLowerCase(ch)){
            ch=Character.toUpperCase(ch);
        }
        else{
            ch=Character.toLowerCase(ch);
        }
    }
    for(int i=0; i<result.length; i++){
        System.out.printf("%c", result[i]);
    }
    }
}

"""
This Is A String
tHIS iS a sTRING
"""
```

### 18. remove characters from a string except alphabets.
```
import java.util.*;

public class string {
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);

    String str=input.nextLine();
    char[] letters=new char[str.length()];
    letters=str.toCharArray();
    for(int i=0; i<letters.length; i++){
        char ch=letters[i];
        if(Character.isLetter(ch)){
            System.out.printf("%c", letters[i]);
        }
    }
    }
}

"""
w3resources.com
wresourcescom
"""
```

### 19.  find the frequency of characters.
```
import java.util.*;

public class string {
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);

    String str=input.nextLine();
    char[] letters=new char[str.length()];
    letters=str.toCharArray();
    char search = input.next().charAt(0);
    int count=0;
    for(int i=0; i<letters.length; i++){
        char ch=letters[i];
        if(ch==search){
            count++;
        }
    }
    System.out.println(count);
    }
}
"""
this is test string
i
3
"""
```

### 20. combine two strings manually.
```
import java.util.*;

public class string {
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);

    String str1=input.nextLine();
    String str2=input.nextLine();
    String result=str1+ " " +str2;
    System.out.println(result);

    }
}

"""
this is string one
this is string two
this is string one this is string two
"""
```

### 21. find the largest and smallest words in a string.
```
import java.util.*;

public class string {
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);

    String str=input.nextLine();
    String[] words=str.split(" ");
    Arrays.sort(words, Comparator.comparingInt(String::length));
    int n=words.length;
    System.out.printf("Largest word is: %s\n", words[n-1]);
    System.out.printf("Smallest word is: %s\n", words[0]);

    }
}
"""
This is a string with smallest and largest words
Largest word is: smallest
Smallest word is: a
"""
```

### 22. convert a string to uppercase.
```
import java.util.*;

public class string {
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);

    String str=input.nextLine();
    str=str.toUpperCase();
    System.out.println(str);

    }
}

"""
The quick brown for jumps over the lazy dog
THE QUICK BROWN FOR JUMPS OVER THE LAZY DOG
"""
```

### 23. convert a string to lowercase.
```
import java.util.*;

public class string {
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);

    String str=input.nextLine();
    str=str.toLowerCase();
    System.out.println(str);

    }
}

"""
THE DOG IS VERY SMART
the dog is very smart
"""
```

### 24. check whether a character is a Hexadecimal Digit or not.
```
import java.util.*;

public class string {
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);

    char ch=input.next().charAt(0);
    if((ch >= '0' && ch<= '9') || (ch >= 'A' && ch <= 'F') || (ch >= 'a' && ch <= 'f')){
        System.out.println("yes");
    }
    else{
        System.out.println("No");
    }

    }
}


"""
H
No
"""
```

### 25. check whether a letter is uppercase or not.
```
import java.util.*;

public class string {
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);

    char ch=input.next().charAt(0);
    if(Character.isUpperCase(ch)){
        System.out.println("yes");
    }
    else{
        System.out.println("No");
    }

    }
}
"""
P
Yes
"""
```
