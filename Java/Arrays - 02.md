### methods
1. int[] newArr=Arrays.copyOf(arr, arr.length) --> copy a array for new array
2. 

### 1. sort a numeric array and a string array.
```
import java.util.*;
public class Main {
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);

        int[] nums=new int[5];
        String[] words=new String[5];
        for(int i=0; i<nums.length; i++){
            nums[i]=input.nextInt();
        }
        for(int i=0; i<words.length; i++){
            words[i]=input.next();
        }
        Arrays.sort(nums);
        Arrays.sort(words);
        for(int i=0; i<nums.length; i++){
            System.out.printf("%d ", nums[i]);
        }
        System.out.printf("\n");
        for(int i=0; i<words.length; i++){
            System.out.printf("%s ", words[i]);
        }
            }
    }
"""
2 4 6 7 8
hi amma how are you
2 4 6 7 8
amma are hi how you
"""
```

### 2.insert an element (specific position) into an array.
```
import java.util.*;
public class Main {
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);

        int[] arr={25,14,56,15,36};
        int pos=2;
        int newElement=35;
        for(int i=arr.length-1; i>pos; i--){
            arr[i]=arr[i-1];
        }
        arr[pos]=newElement;
        for(int i=0; i<arr.length; i++){
            System.out.printf("%d ", arr[i]);
        }
    }
    }
"""
25 14 35 56 15
"""
```
* in the above solution last element is missing.

```
import java.util.*;
public class Main {
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);

        int[] arr={25,14,56,15,36};
        int pos=2;
        int newElement=35;
        int[] newArr=new int[arr.length+1];
        for(int i=0; i<pos; i++){
            newArr[i]=arr[i];
        }
        newArr[pos]=newElement;
        for(int i=pos; i<arr.length; i++){
            newArr[i+1]=arr[i];
        }
        for(int i=0; i<newArr.length; i++){
            System.out.printf("%d ", newArr[i]);
        }
    }
    }
"""
25 14 35 56 15 36
"""
```
* Here, last element also added

### 3. sort an array of integers
```
import java.util.*;
public class Main {
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);

        Integer[] arr={25,14,56,15,36,56,77,18,29,49};
        Arrays.sort(arr, Collections.reverseOrder());
        for(int i=0; i<arr.length; i++){
            System.out.printf("%d ", arr[i]);
        }
        
    }
    }
"""
77 56 56 49 36 29 25 18 15 14
"""
```
