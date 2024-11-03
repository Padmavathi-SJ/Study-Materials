### methods
1. int[
 newArr=Arrays.copyOf(arr, arr.length) --> copy a array for new array

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
