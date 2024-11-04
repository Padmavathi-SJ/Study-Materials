### methods:
1. str1.contentEquals(str2) ---> it will consider case also and compare , like equals() method only
2. String.copyValueOf(arr_nums, 1, 3); --> from which arr, startIndex, endIndex
3. str.endsWith(end_str) --> To check the string is ending with given end string
4. str.startsWith(start_str) --> To check the string is starting with given start string.
5. byte[] byte_arr=str.getBytes(); ---> convert and store a string into bytes array.
6. int hash_code = str.hashCode(); --> to get a hash code of a string
7. str.substring(10(startIndex), 26(endIndex))--> to extract a substring from a substring
8. str.trim() --> to remove leading and trailing spaces
9. str.setCharAt(index, value) --> to assign value to stringBuilder



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

### 7. concatenate a given string to the end of another string.
```
import java.util.*;
public class Main {
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);

        String str1=input.nextLine();
        String str2=input.nextLine();
        System.out.println(str1 + " " + str2);
        
    }
}
"""
PHP Exercises and
Python Exercises
PHP Exercises and Python Exercises
"""
```

### 8. test if a given string contains the specified sequence of char values.
```
import java.util.*;
public class Main {
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);

        String str=input.nextLine();
        String search=input.nextLine();
        boolean result=str.contains(search);
        System.out.println(result);
        
    }
}
"""
PHP Exercises and Python Exercises //str
and //search
true
"""
```

### 9. compare a given string to the specified character sequence.
```
import java.util.*;
public class Main {
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);

        String str1=input.nextLine();
        String str2=input.nextLine();
        boolean result=str1.contentEquals(str2); //str1.equals(str2)
        System.out.println(result);
        
    }
}
"""
example.com
Example.com
false
"""
```

### 10. compare a given string to a specified string buffer.
```
import java.util.*;
public class Main {
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);

        String str1=input.nextLine();
        String str2=input.nextLine();
        StringBuffer strbuff=new StringBuffer(str1);
        System.out.println(str1.contentEquals(strbuff));
        System.out.println(str2.contentEquals(strbuff));
        
    }
}
"""
example.com
Example.com
true
false
"""
```

### 11. create a String object with a character array.
```
import java.util.*;
public class Main {
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);

        char[] arr_nums={'1', '2', '3', '4'};
        String str=String.copyValueOf(arr_nums, 1, 3);
        System.out.println("The book contains " + str + " pages");        
    }
}
"""
The book contains 234 pages
"""
```

### 12. check whether a given string ends with another string.
```
import java.util.*;
public class Main {
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);

        String str=input.nextLine() ;
        String end_str=input.nextLine();
        boolean result=str.endsWith(end_str);
        System.out.println(result);       
    }
}
"""
Python Exercises //str
se //end_str
false
"""
```

### as well as starting string also
```
import java.util.*;
public class Main {
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);

        String str=input.nextLine() ;
        String start_str=input.nextLine();
        boolean result=str.startsWith(start_str);
        System.out.println(result);       
    }
}
"""
Python Exercises!
Py
true
"""
```

### 13. check whether two String objects contain the same data.
```
import java.util.*;
public class Main {
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);

        String str=input.nextLine() ;
        String str2=input.nextLine();
        boolean result=str.equals(str2);
        System.out.println(result);       
    }
}
"""
Hi amma how are you
Hi amma how are you
true
"""
```
### 14. print the current date and time in the specified format.
```
import java.util.*;
public class Main {
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);

        Calendar c=Calendar.getInstance();   
        System.out.printf("%tB %te, %tY\n", c, c, c);
        System.out.printf("%tl:%tM %tp\n", c, c, c);   
    }
}
"""
November 1, 2024
10:30 pm //according to our system time
"""
```

### 15.get the contents of a given string as a byte array.
```
import java.util.*;
public class Main {
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);

        String str="This is a sample string";
        byte[] byte_arr=str.getBytes();
        String newStr=new String(byte_arr);
        System.out.println(newStr);
    }
}
"""
This is a sample string //byte string
"""
```

### 16. create a distinct identifier for a given string.
```
import java.util.*;
public class Main {
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);

        String str="This is a sample string";
        int hash_code=str.hashCode();
        System.out.println(hash_code);
    }
}
"""
-2020443276 //hash code of our string
"""
```


### 17. replace each substring of a given string that matches the given regular expression with the given replacement.
```
import java.util.*;
public class Main {
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);

        String str=input.nextLine();
        String new_str=str.replaceAll("fox", "cat");
        System.out.println(str);
        System.out.println("modifies string: " + new_str);
    }
}
"""
The quick brown fox jumps overthe lazy dog
modifies string: The quick brown cat jumps overthe lazy dog
"""
```
### 18.check whether a given string starts with another string.
```
import java.util.*;
public class Main {
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);

        String str=input.nextLine();
        String start_str=input.nextLine();
        boolean result=str.startsWith(start_str);
        System.out.println(result);
    }
}
"""
Orange is my favorite color
Red
false
"""
```
### 19.  trim leading or trailing whitespace from a given string.
```
import java.util.*;
public class Main {
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);

        String str=input.nextLine();
        str=str.trim();
        System.out.println(str);
    }
}
"""
   hi di mamma  
hi di mamma
"""
```

### 20.  find the second most frequent character in a given string.
```
import java.util.*;
public class Main {
    public static char findSecChar(String str){
        int[] count=new int[256];
        for(int i=0; i<str.length(); i++){
            (count[str.charAt(i)])++;
        }
        int charFirst=0;
        int charSec=0;
        for(int i=0; i<256; i++){
            if(count[i] > count[charFirst]){
                charSec=charFirst;
                charFirst=i;
            }
            else if(count[i] > count[charSec] && count[i]!=count[charFirst]){
                charSec=i;
            }
        }
        return (char) charSec;
    }
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);

        String str=input.nextLine();
        char result=findSecChar(str);
        System.out.println(result);
    }
}
"""
successes
c
"""
```
### 21. find the length of the longest substring of a given string without repeating characters.
```
import java.util.*;
public class Main {
    public static boolean allUniqueChar(String str, int start, int end){
        boolean[] charSet=new boolean[256];
        for(int i=start; i<=end; i++){
            char ch=str.charAt(i);
            if(charSet[ch]){
                return false;
            }
            charSet[ch]=true;
        }
        return true;
    }
    public static int findLongSubString(String str){
        int maxLength=0;
        for(int i=0; i<str.length(); i++){
            for(int j=i; j<str.length(); j++){
                if(allUniqueChar(str, i, j)){
                    maxLength=Math.max(maxLength, j-i+1);
                }
            }
        }
        return maxLength;
    }
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);

        String str=input.nextLine();
        int maxLength=findLongSubString(str);
        System.out.println(maxLength);
    }
}
"""
pickoutthelongestsubstring
8
"""
```

### 22. print the result of removing duplicates from a given string.
```
import java.util.*;
public class Main {
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);

        String str=input.nextLine();
        char[] letters=str.toCharArray();
        for(int i=0; i<letters.length; i++){
            if(letters[i]!='\0'){
            for(int j=i+1; j<letters.length; j++){
                if(letters[i] == letters[j]){
                    letters[j]='\0';
                }
            }
        }
        }
        for(int i=0; i<letters.length; i++){
            System.out.printf("%c", letters[i]);
        }
    }
}
"""
w3resources
w3resouc
"""
```

### 23. find the first non-repeating character in a string.
```
import java.util.*;
public class Main {
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);

        String str=input.nextLine();
        char[] letters=str.toCharArray();
        for(int i=0; i<letters.length; i++){
            boolean flag=true;
            for(int j=i+1; j<letters.length; j++){
                if(letters[i] == letters[j]){
                    flag=false;
                }
            }
            if(flag){
                System.out.println(letters[i]);
                break;
            }
        }
        }
    }
"""
gibblegabbler
i
"""
```

### 24. print a list of items containing all characters of a given word.
```
import java.util.*;
public class Main {
    public static boolean containsAllCharacters(String str, String search){
        char[] letters=search.toCharArray();
        for(int i=0; i<letters.length; i++){
            char ch=letters[i];
            if(str.indexOf(ch) == -1){
                return false;
            }
        }
        return true;
    }
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);

        String str=input.nextLine();
        String[] words=str.split("\\s+");
        String search=input.nextLine();
        for(int i=0; i<words.length; i++){
            if(containsAllCharacters(words[i], search)){
                System.out.println(words[i]);
            }
        }
        }
    }
"""
rabbit bribe dog
bib
rabbit
bribe
"""
```

### 25.  find the character in a string that occurs the most frequently.
```
import java.util.*;
public class Main {
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);

        String string=input.nextLine();
        StringBuilder str=new StringBuilder(string);
        int maxCount=1;
        int maxIndex=0;
        char maxChar = str.charAt(0);
        for(int i=0; i<str.length(); i++){
            if(str.charAt(i) != '\0'){
            int count=1;
            for(int j=i+1; j<str.length(); j++){
                if(str.charAt(i) ==  str.charAt(j)){
                    count++;
                    str.setCharAt(j, '\0');
                }
            }
            if(count > maxCount){
                maxCount=count;
                maxIndex=i;
                maxChar=str.charAt(maxIndex);
            }
        }
    }
        System.out.println(maxChar);
        }
    }
"""
test string
t
"""
```

### 26. reverse every word in a string using methods.
```
import java.util.*;
public class Main {
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);

        String str=input.nextLine();
        String[] words=str.split("\\s+");
        for(int i=0; i<words.length; i++){
            String currStr=words[i];
            for(int j=currStr.length()-1; j>=0; j--){
                System.out.printf("%c", currStr.charAt(j));
            }
            System.out.printf(" ");
        }
        }
    }
"""
This is a string
sihT si a gnirts
"""
```

### 27. count and print all duplicates in the input string.
```
import java.util.*;
public class Main {
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);

        String str=input.nextLine();
        char[] letters=str.toCharArray();
        for(int i=0; i<letters.length; i++){
            if(letters[i]!='\0'){
            int count=1;
            for(int j=i+1; j<letters.length; j++){
                if(letters[i] == letters[j]){
                    count++;
                    letters[j]='\0';
                }
            }
            if(count >= 2){
            System.out.printf("%c appears %d times\n", letters[i], count);
        }}
    }
        }
    }
"""
w3resources
r appears 2 times
e appears 2 times
s appears 2 times
"""
```

### 28. check if two given strings are rotations of each other.
```
import java.util.*;
public class Main {
    public static boolean rotationsOfStrings(String str1, String str2){
        if((str1.length() == str2.length()) && (str1 + str2).indexOf(str2) != -1){
            return true;
        }
        return false;
    }
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);

        String str1=input.nextLine();
        String str2=input.nextLine();
        if(rotationsOfStrings(str1, str2)){
            System.out.printf("The 2nd string %s exists in the new string.\n Strings are rotations of each other", str2);
        }
        else{
            System.out.printf("The 2nd string %s does not exists in the new string.\n Strings are rotations of each other", str2);
        }
        }
    }
"""
```

### 29. remove all adjacent duplicates recursively from a given string.
```
import java.util.*;
public class Main {
    public static String removeDuplicates(String str){
     if(str.length() <= 1){
        return str;
     }
     StringBuilder result=new StringBuilder();
     boolean hasDuplicates=false;
     for(int i=0; i<str.length(); i++){
        if(i < str.length()-1 && (str.charAt(i) == str.charAt(i+1))){
            hasDuplicates=true;
            i++;
        }
        else{
            result.append(str.charAt(i));
        }
    }
        if(!hasDuplicates){
            return result.toString();
        }
        return removeDuplicates(result.toString());
    }
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);

        String str=input.nextLine();
        String result = removeDuplicates(str);
        System.out.println(result);
        }
    }
"""
aabaarbarccrabmq
brmq
"""
```
```

ABACD
CDABA
The 2nd string CDABA exists in the new string.
 Strings are rotations of each other.
"""
```

### 31. appends two strings, omitting one character if the concatenation creates double characters.
```
import java.util.*;
public class Main {
    public static String concat(String str1, String str2){
        if(str1.length() != 0 && str2.length() != 0 && (str1.charAt(str1.length()-1) == str2.charAt(0))){
            return str1 + str2.substring(1);
        }
        return str1+str2;
    }
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);

        String str1=input.nextLine();
        String str2=input.nextLine();
        String result=concat(str1, str2);
        System.out.println(result);
        }
    }
"""
food
door
foodoor
"""
```

### 32. create a string from a given string by swapping the last two characters of the given string. The string length must be two or more.
```
import java.util.*;
public class Main {
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);

        String str=input.nextLine();
        StringBuilder result=new StringBuilder(str);
        if(result.length() >= 2){
            char lastChar=result.charAt(result.length()-1);
            result.setCharAt(result.length()-1, result.charAt(result.length()-2));
            result.setCharAt(result.length()-2, lastChar);
        }
        str=new String(result);
        System.out.println(str);
        }
    }
"""
string
strign
"""
```

### 33.reverses all odd-length words in a string.
```
import java.util.*;
public class Main {
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);

        String str=input.nextLine();
        String[] words=str.split("\\s+");
        for(int i=0; i<words.length; i++){
            if((words[i].length()-1) % 2 != 0){
                String currStr=words[i];
                for(int j=currStr.length()-1; j>=0; j--){
                    System.out.printf("%c", currStr.charAt(j));
                }
                System.out.printf(" ");
            }
            else{
                System.out.printf("%s ", words[i]);
            }
        }
            }
    }
"""
Create a Date object using the Calendar class
etaerC a etaD tcejbo using the radnelaC class
"""
```

### 34.check whether there are two consecutive (following each other continuously), identical letters in a given string.
```
import java.util.*;
public class Main {
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);

        String str=input.nextLine();
        boolean flag=false;
        for(int i=0; i<str.length()-1; i++){
            if(str.charAt(i) == str.charAt(i+1)){
                flag=true;
            }
        }
        if(flag){
            System.out.println("true");
        }
        else{
            System.out.println("false");
        }
            }
    }
"""
Yellow
true
"""
```

### 35. concatenate a given string with itself a given number of times.
```
import java.util.*;
public class Main {
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);

        String str=input.nextLine();
        int num_of_time=input.nextInt();
        StringBuilder result=new StringBuilder();
        int i=0;
        while(i<num_of_time){
            result.append(str);
            i++;
        }
        System.out.println(result);
            }
    }
"""
PHP
7
PHPPHPPHPPHPPHPPHPPHP
"""
```

### 36. sort the string by length
```
import java.util.*;
public class Main {
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);

        String str=input.nextLine();
        String[] words=str.split("\\s+");
        Arrays.sort(words, Comparator.comparingInt(String::length));
        for(int i=0; i<words.length; i++){
            System.out.printf("%s ", words[i]);
        }
        
            }
    }
"""
love you I
I you love
"""
```

### 37. print longest palindromic substring from a given string
```
import java.util.*;
public class Main {
    public static boolean checkPalindrome(String str, int start, int end){
        while(start < end){
            if(str.charAt(start) != str.charAt(end)){
                return false;
            }
            start++;
            end--;
        }
        return true;
    }
    public static String longPalinSubstring(String str){
        int maxLength=1;
        int n=str.length();
        int start=0;
        for(int i=0; i<n; i++){
            for(int j=i+1; j<n; j++){
                if(checkPalindrome(str, i, j)){
                    if(j-i+1 > maxLength){
                        maxLength=j-i+1;
                        start=i;
                    }
                }
            }
        }
        StringBuilder newStr=new StringBuilder();
        for(int i=start; i<=start+maxLength; i++){
            newStr.append(str.charAt(i));
        }
        return newStr.toString();
    }
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);

    
       String str=input.nextLine();
       String result=longPalinSubstring(str);
       System.out.println(result);
    }
}
"""
babad
baba
"""
```

### 38. check a given string is palindrome or not?
```
import java.util.*;
public class Main {
    public static boolean palindromeOrNot(String str){
        int n=str.length();
        int start=0;
        int end=n-1;
        while(start < end){
            if(str.charAt(start) != str.charAt(end)){
                return false;
            }
            start++;
            end--;
        }
        return true;
    }
        public static void main(String[] args){
        Scanner input=new Scanner(System.in);

    
       String str=input.nextLine();
       boolean result=palindromeOrNot(str);
       System.out.println(result);
    }
}
"""
padma
false

madam
true
"""
```

### 39. check whether the two strings are anagrams or not
```
import java.util.*;
public class Main {
    public static boolean areAnagrams(String str1, String str2){
        int[] count1=new int[256];
        int[] count2=new int[256];

        for(int i=0; i<str1.length(); i++){
            count1[str1.charAt(i)]++;
        }
        for(int i=0; i<str2.length(); i++){
            count2[str2.charAt(i)]++;
        }
        for(int i=0; i<256; i++){
            if(count1[i] != count2[i]){
                return false;
            }
        }
        return true;
    }
        public static void main(String[] args){
        Scanner input=new Scanner(System.in);

    
       String str1=input.nextLine();
       String str2=input.nextLine();
       boolean result=areAnagrams(str1, str2);
       System.out.println(result);
    }
}
"""
dog
god
true
"""
```

### 40. check whether the given string is pangram or not?
```
import java.util.*;
public class Main {
    public static boolean isPangram(String str){
        boolean[] alphabet=new boolean[26];
        for(int i=0; i<26; i++){
            alphabet[i]=false;
        }
        for(int i=0; i<str.length(); i++){
            char ch=str.charAt(i);
            int index=ch - 'a';
            alphabet[index]=true;
        }
        for(int i=0; i<26; i++){
            if(alphabet[i]==false){
                return false;
            }
        }
        return true;

    }
        public static void main(String[] args){
        Scanner input=new Scanner(System.in);

    
            String str=input.nextLine();
            boolean result=isPangram(str);
            System.out.println(result);
    }
}
"""
qwertyuiopasdfghjklzxcvbnm
true

padma
false
"""
```
