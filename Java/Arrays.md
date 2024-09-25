## Arrays:

### print an array:
```
import java.util.*;
public class Main{
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        
    int n=input.nextInt();
    int[] arr=new int[n];
    for(int i=0; i<n; i++){
        arr[i]=input.nextInt();
    }
    for(int i=0; i<n; i++){
        System.out.printf("%d ", arr[i]);
    }
    input.close();
}
}
"""
5
1 2 3 4 5
1 2 3 4 5
"""
```

### print all negative elements in an array.
```
import java.util.*;
public class Main{
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        
    int n=input.nextInt();
    int[] arr=new int[n];
    for(int i=0; i<n; i++){
        arr[i]=input.nextInt();
    }
    for(int i=0; i<n; i++){
        if(arr[i]<0){
        System.out.printf("%d ", arr[i]);
    }
    }
    input.close();
}
}
"""
5
1 -2 -3 -4 5
-2 -3 -4
"""
```
### sum of all array elements.
```
import java.util.*;
public class Main{
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        
    int n=input.nextInt();
    int[] arr=new int[n];
    for(int i=0; i<n; i++){
        arr[i]=input.nextInt();
    }
    int sum=0;
    for(int i=0; i<n; i++){
       sum+=arr[i];
    }
    System.out.printf("%d", sum);
    input.close();
}
}
"""
5
1 2 3 4 5
15
"""
```

### find maximum and minimum element in an array
```
import java.util.*;
public class Main{
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        
    int n=input.nextInt();
    int[] arr=new int[n];
    for(int i=0; i<n; i++){
        arr[i]=input.nextInt();
    }
    
    for(int i=0; i<n; i++){
        for(int j=i+1; j<n; j++){
        if(arr[i]>arr[j]){
      int temp=arr[i];
      arr[i]=arr[j];
      arr[j]=temp;
    }
   }
    }
    
    System.out.println("min is: " + arr[0]);
    System.out.println("max is: " + arr[n-1]);
    
    input.close();
}
}
"""
5
4 6 8 1 6
mis is 1
max is 8
"""
```

### find second largest element in an array.
```
import java.util.*;
public class Main{
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        
    int n=input.nextInt();
    int[] arr=new int[n];
    for(int i=0; i<n; i++){
        arr[i]=input.nextInt();
    }
    
    for(int i=0; i<n; i++){
        for(int j=i+1; j<n; j++){
        if(arr[i]>arr[j]){
      int temp=arr[i];
      arr[i]=arr[j];
      arr[j]=temp;
    }
   }
    }
    
    System.out.println("second largest is: " + arr[n-2]);
    
    input.close();
}
}
"""
5
4 8 6 7 1
second largest is: 7
"""
```
### count total number of even and odd elements in an array.
```
import java.util.*;
public class Main{
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        
    int n=input.nextInt();
    int[] arr=new int[n];
    for(int i=0; i<n; i++){
        arr[i]=input.nextInt();
    }
    
   int oddCount=0;
   int evenCount=0;
   
   for(int i=0; i<n; i++){
       if(arr[i]%2==0){
           evenCount++;
       }
       else if(arr[i]%2!=0){
           oddCount++;
       }
   }
   
   System.out.println("odd numbers: " + oddCount);
   System.out.println("even numbers: " + evenCount);
    
    input.close();
}
}
"""
6
1 3 4 5 6 7
odd numbers: 4
even numbers: 2
"""
```

### left rotate an array (left to right):
```
import java.util.*;
public class Main{
    
    public static void rotateArr(int[] arr, int n){
        int temp=arr[0];
        for(int i=0; i<n-1; i++){
           arr[i]=arr[i+1];
        }
        arr[n-1]=temp;
    }
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        
    int n=input.nextInt();
    int[] arr=new int[n];
    for(int i=0; i<n; i++){
        arr[i]=input.nextInt();
    }
    int k=3;
    for(int i=0; i<k; i++){
        rotateArr(arr,n);
    }
    for(int i=0; i<n; i++){
        System.out.printf("%d ", arr[i]);
    }
    input.close();
}
}
"""
10
1 2 3 4 5 6 7 8 9 10
4 5 6 7 8 9 10 1 2 3
"""
```

### right rotate an array (right to left):
```
import java.util.*;
public class Main{
    
    public static void rotateArr(int[] arr, int n){
        for(int i=0; i<n-1; i++){
         int temp=arr[i];
         arr[i]=arr[n-1];
         arr[n-1]=temp;
        }
    }
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        
    int n=input.nextInt();
    int[] arr=new int[n];
    for(int i=0; i<n; i++){
        arr[i]=input.nextInt();
    }
    int k=3;
    for(int i=0; i<k; i++){
        rotateArr(arr,n);
    }
    for(int i=0; i<n; i++){
        System.out.printf("%d ", arr[i]);
    }
    input.close();
}
}
"""
10
1 2 3 4 5 6 7 8 9 10
8 9 10 1 2 3 4 5 6 7
"""
```

## MATRIX(2D array):

### print a matrix:
```
import java.util.*;
public class Main{
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        
    int r=3;
    int c=3;
    int[][] m1=new int[r][c];
    for(int i=0; i<r; i++){
        for(int j=0; j<c; j++){
            m1[i][j]=input.nextInt();
        }
    }
    
    for(int i=0; i<r; i++){
        for(int j=0; j<c; j++){
            System.out.printf("%d ", m1[i][j]);
        }
        System.out.printf("\n");
    }
    
    input.close();
}
}
"""
1 2 3
4 5 6
7 8 9

1 2 3
4 5 6
7 8 9
"""
```

### get input as a char array:
```
import java.util.*;
public class Main{
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        
        int n=input.nextInt();
        int[] arr=new int[n];
        for(int i=0; i<n; i++){
            arr[i]=input.next().charAt(0);
        }
        for(int i=0; i<n; i++){
            System.out.printf("%c ", arr[i]);
        }
        input.close();
    }
}
"""
5
A B C D E
A B C D E
"""
```
### sort an array as odd elements and even elements:
```
import java.util.*;
public class Main{
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        
        int n=input.nextInt();
        int[] arr=new int[n];
        
        for(int i=0; i<n; i++){
            arr[i]=input.nextInt();
        }
        
        int oddCount=0,evenCount=0;
        for(int i=0; i<n; i++){
            if(arr[i]%2!=0){
                oddCount++;
            }
            else{
            evenCount++;
            }
        }
        
        int[] oddArr=new int[oddCount];
        int[] evenArr=new int[evenCount];
        
        int oddIndex=0,evenIndex=0;
        
        for(int i=0; i<n; i++){
            if(arr[i]%2!=0){
                oddArr[oddIndex++]=arr[i];
            }
            else{
                evenArr[evenIndex++]=arr[i];
            }
        }
        
        int l=evenCount+oddCount;
        int[] combined=new int[l];
        
        for(int i=0; i<oddCount; i++){
            combined[i]=oddArr[i];
        }
        for(int i=0; i<evenCount; i++){
            combined[oddCount+i]=evenArr[i];
    }
    for(int i=0; i<l; i++){
        System.out.printf("%d ", combined[i]);
    }
    input.close();
}
}
"""
10
1 2 3 4 5 6 7 8 9 10
1 3 5 7 9 2 4 6 8 10
"""
```

### merge two arrays:
```
import java.util.*;
public class Main{
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        
        int n=input.nextInt();
        int[] arr1=new int[n];
        
        for(int i=0; i<n; i++){
            arr1[i]=input.nextInt();
        }
        
        int m=input.nextInt();
        int[] arr2=new int[m];
        for(int i=0; i<m; i++){
            arr2[i]=input.nextInt();
        }
        
        int l=n+m;
        int[] merged=new int[l];
        int index=0;
        for(int i=0; i<n; i++){
            merged[index++]=arr1[i];
        }
        for(int i=0; i<m; i++){
            merged[n+i]=arr2[i];
        }
        
        for(int i=0; i<l; i++){
            System.out.printf("%d ", merged[i]);
        }
        
        
    input.close();
}
}
"""
5
1 2 3 4 5
5
6 7 8 9 10
1 2 3 4 5 6 7 8 9 10
"""
```
###
```
import java.util.*;
public class Main{
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        
        int n=input.nextInt();
        int[] arr=new int[n];
        
        for(int i=0; i<n; i++){
            arr[i]=input.nextInt();
        }
        
        int dupCount=0;
        for(int i=0; i<n; i++){
            if(arr[i]!='\0'){
            for(int j=i+1; j<n; j++){
                if(arr[i]==arr[j]){
                    dupCount++;
                    arr[j]='\0';
                }
            }
            }
        }
        
        System.out.printf("%d", dupCount);
    input.close();
}
}
"""
6
1 2 2 4 4 5
2
"""
```

### find subarrays of an array:
```
import java.util.*;
public class Main{
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        
        int n=input.nextInt();
        int[] arr=new int[n];
        
        for(int i=0; i<n; i++){
            arr[i]=input.nextInt();
        }
        
        for(int start=0; start<n; start++){
            for(int end=start; end<n; end++){
                for(int k=start; k<=end; k++){
                    System.out.printf("%d ", arr[k]);
                }
                System.out.printf("\n");
            }
        }
    input.close();
}
}
"""
3
1 2 3
1
1 2
1 2 3
2
2 3
3
"""
```

### maximum sum of subarray:
```
import java.util.*;
public class Main{
    public static int maxSubArrSum(int[] arr, int n){
        int maxSum=arr[0];
        int currSum=arr[0];
        for(int i=1; i<n; i++){
            currSum=Math.max(arr[i], currSum+arr[i]);
            maxSum=Math.max(maxSum, currSum);
        }
        return maxSum;
    }
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        
        int n=input.nextInt();
        int[] arr=new int[n];
        
        for(int i=0; i<n; i++){
            arr[i]=input.nextInt();
        }
        
        int maxSum=maxSubArrSum(arr, n);
        System.out.printf("%d", maxSum);
    input.close();
}
}
"""
4
-2 1 -3 4
4
"""
```
### Find the Largest Element in an Array
```
import java.util.*;
public class Main{
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        
        int n=input.nextInt();
        int[] arr=new int[n];
        
        for(int i=0; i<n; i++){
            arr[i]=input.nextInt();
        }
       
       int max=arr[0];
       for(int i=1; i<n; i++){
           if(arr[i]>max){
               max=arr[i];
           }
       }
       System.out.printf("%d", max);
    input.close();
}
}
"""
5
8 9 4 7 5
9
"""
```
### Check if Array is Sorted
```
import java.util.*;
public class Main{
    public static boolean isSorted(int[] arr){
        int n=arr.length;
        for(int i=0; i<n-1; i++){
            if(arr[i]>arr[i+1]){
                return false;
            }
        }
        return true;
    }
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        
        int n=input.nextInt();
        int[] arr=new int[n];
        
        for(int i=0; i<n; i++){
            arr[i]=input.nextInt();
        }
       
       if(isSorted(arr)){
           System.out.printf("yes\n");
       }
       else{
            System.out.printf("No\n");
       }
    input.close();
}
}
"""
5
8 9 5 4 6
No
"""
```
### Remove Duplicates from an Array
```
import java.util.*;
public class Main{
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        
        int n=input.nextInt();
        int[] arr=new int[n];
        for(int i=0; i<n; i++){
            arr[i]=input.nextInt();
        }

       for(int i=0; i<n; i++){
           if(arr[i]!='\0'){
           for(int j=i+1; j<n; j++){
               if(arr[i]==arr[j]){
                   arr[j]='\0';
               }
           }
           }
       }
       for(int i=0; i<n; i++){
           if(arr[i]!='\0'){
               System.out.printf("%d ", arr[i]);
           }
       }
       
    input.close();
}
}
"""
6
1 2 2 3 4 4
1 2 3 4
"""
```

### Merge Two Sorted Arrays
```
import java.util.*;
public class Main{
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        
        int n=input.nextInt();
        int[] arr1=new int[n];
        for(int i=0; i<n; i++){
            arr1[i]=input.nextInt();
        }
        
        int m=input.nextInt();
        int[] arr2=new int[m];
        for(int i=0; i<m; i++){
            arr2[i]=input.nextInt();
        }
        
        int l=n+m;
        int index=0;
        int[] merged=new int[l];
        
        for(int i=0; i<n; i++){
            merged[index++]=arr1[i];
        }
        for(int i=0; i<m; i++){
            merged[index+i]=arr2[i];
        }
       for(int i=0; i<l; i++){
           for(int j=i+1; j<l; j++){
               if(merged[i]>merged[j]){
                   int temp=merged[i];
                   merged[i]=merged[j];
                   merged[j]=temp;
               }
           }
       }
       
       for(int i=0; i<l; i++){
           System.out.printf("%d ", merged[i]);
       }
    input.close();
}
}
"""
3
1 3 5
3
2 4 6
1 2 3 4 5 6
"""
```

### Move Zeros to End
``` 
import java.util.*;
public class  Main{
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        
        int n=input.nextInt();
        int[] arr=new int[n];
        for(int i=0; i<n; i++){
            arr[i]=input.nextInt();
        }
        int nonZeroCount=0;
        for(int i=0; i<n; i++){
            if(arr[i]!=0){
                nonZeroCount++;
            }
        }
        int nonZeroIndex=0;
        int[] nonZeroArr=new int[n];
        
        for(int i=0; i<n; i++){
            if(arr[i]!=0){
                nonZeroArr[nonZeroIndex++]=arr[i];
            }
        }
        for(int i=nonZeroCount; i<n; i++){
            nonZeroArr[i]=0;
        }
        for(int i=0; i<n; i++){
            System.out.printf("%d ", nonZeroArr[i]);
        }
        input.close();
    }
}
"""
5
0 1 0 3 12
1 3 12 0 0
"""
```

### Product of Array Except Self
```
import java.util.*;
public class  Main{
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        
        int n=input.nextInt();
        int[] arr=new int[n];
        for(int i=0; i<n; i++){
            arr[i]=input.nextInt();
        }
      int[] productArr=new int[n];
      int product=1;
      int index=0;
      for(int i=0; i<n; i++){
          for(int j=0; j<n; j++){
              if(i!=j){
                  product=product*arr[j];
              }
          }
          productArr[index++]=product;
          product=1;
      }
      
      for(int i=0; i<n; i++){
          System.out.printf("%d ", productArr[i]);
      }
        input.close();
    }
}
"""
4
1 2 3 4
24 12 8 6
"""
```

### Find the Duplicate Number
```
import java.util.*;
public class  Main{
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        
        int n=input.nextInt();
        int[] arr=new int[n];
        for(int i=0; i<n; i++){
            arr[i]=input.nextInt();
        }
        int found=0;
     for(int i=0; i<n; i++){
         for(int j=i+1; j<n; j++){
             if(arr[i]==arr[j]){
                 found=1;
                 System.out.println(arr[i]);
                 input.close();
             }
         }
     }
     if(found==0){
     System.out.println("No duplicates are found");
     }
        input.close();
    }
}
"""
5
1 3 4 2 2
2
"""
```
### Sort Colors:
```
import java.util.*;
public class  Main{
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        
        int n=input.nextInt();
        int[] arr=new int[n];
        for(int i=0; i<n; i++){
            arr[i]=input.nextInt();
        }
        Arrays.sort(arr);
        for(int i=0; i<n; i++){
            System.out.printf("%d ", arr[i]);
        }
        input.close();
    }
}
"""
6
2 0 2 1 1 0
0 0 1 1 2 2
"""
```

### print Values equal to index value
```
import java.util.*;
public class  Main{
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        
        int n=input.nextInt();
        int[] arr=new int[n+1];
        for(int i=1; i<=n; i++){
            arr[i]=input.nextInt();
        }
        for(int i=1; i<=n; i++){
            if(arr[i]==i){
            System.out.printf("%d ", arr[i]);
        }
        }
        input.close();
    }
}
"""
5
15 2 45 4 7
2 4
"""
"""
1
1
1
"""
```
* if our array is 1 based index means, take the size+1.

### print Alternates in an Array
```
import java.util.*;
public class  Main{
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        
        int n=input.nextInt();
        int[] arr=new int[n];
        for(int i=0; i<n; i++){
            arr[i]=input.nextInt();
        }
        for(int i=0; i<n; i+=2){
           System.out.printf("%d ", arr[i]);
        }
        input.close();
    }
}
"""
5
1 2 3 4 5
1 3 5
"""
```

### check our arrayis palindromic array or not:
```
import java.util.*;
public class  Main{
    public static boolean isPalindrome(int n){
        int orgNum=n;
        int rev=0;
        while(n!=0){
            int digit=n%10;
            rev=rev*10+digit;
            n/=10;
        }
        return orgNum==rev;
    }
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        
        int n=input.nextInt();
        int[] arr=new int[n];
        for(int i=0; i<n; i++){
            arr[i]=input.nextInt();
        }
        boolean flag=true;
        for(int i=0; i<n; i++){
           if(!isPalindrome(arr[i])){
               flag=false;
               break;
           }
           }
        if(flag){
            System.out.printf("array is a palindromic array\n");
        }
        else{
            System.out.printf("array is not  palindromic arrar.\n");
        }
        input.close();
    }
}
"""
3
111 2222 333
"""
```

### Count of smaller elements
```
import java.util.*;
public class  Main{
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        
        int n=input.nextInt();
        int[] arr=new int[n];
        for(int i=0; i<n; i++){
            arr[i]=input.nextInt();
        }
        int max=input.nextInt();
        int count=0;
        for(int i=0; i<n; i++){
            if(arr[i]<=max){
                count++;
            }
        }
        System.out.printf("%d", count);
        input.close();
    }
}
"""
6
10 1 2 8 4 5
9 //max
5 //count of smaller elements
"""
```

### Swap kth elements
```
import java.util.*;
public class  Main{
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        
        int n=input.nextInt();
        int[] arr=new int[n];
        for(int i=0; i<n; i++){
            arr[i]=input.nextInt();
        }
        int k=3;
        if(k<=0 || k>n){
            System.out.printf("invalid k position");
        }
        else{
        int temp=arr[k-1]; //kth element from start
        arr[k-1]=arr[n-k]; //kth element from end
        arr[n-k]=temp;
        }
        
        for(int i=0; i<n; i++){
           System.out.printf("%d ", arr[i]);
        }
        input.close();
    }
}
"""
8
1 2 3 4 5 6 7 8
1 2 6 4 5 3 7 8 swapped 3 and 6
"""
```

### Display longest name
```
import java.util.*;
public class  Main{
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        
        int n=input.nextInt();
        String[] names=new String[n];
        for(int i=0; i<n; i++){
            names[i]=input.next();
        }
        
        String maxLengthName=names[0];
        for(int i=1; i<n; i++){
            if(names[i].length()>maxLengthName.length()){
                maxLengthName=names[i];
            }
        }
        System.out.println(maxLengthName);
        input.close();
    }
}
"""
5
Geek geeks geeksfor geeksfor geeksforgeeks
geeksforgeeks
"""
```

### sort an array using "Arrays.sort(ArrayName)"
```
import java.util.*;
public class Main{
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        
        int[] arr={5,4,8,1,6,9};
        Arrays.sort(arr);
        for(int i=0; i<arr.length; i++){
            System.out.printf("%d ", arr[i]);
        }
        input.close();
    }
}
"""
1 4 5 6 8 9
"""
```

### copy the array elements to the new array using "Arrays.copyOf(OldArrayName, OldArrayLength)"
```
import java.util.*;
public class Main{
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        
        int[] arr={1,2,3,4,5,6};
        int[] newArr=Arrays.copyOf(arr, arr.length);
        for(int i=0; i<arr.length; i++){
            System.out.printf("%d ", newArr[i]);
        }
        input.close();
    }
}
"""
1 2 3 4 5 6
"""
```


### Copy an array elements between a range  using Arrays.copyOfRange(arrayName, fromIndex(inclusive), toIndex(exclusive))":
```
import java.util.*;
public class Main{
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        
        int[] arr={1,2,3,4,5,6,7};
        int[] newArr=Arrays.copyOfRange(arr, 0, 3);
        for(int i=0; i<newArr.length; i++){
            System.out.printf("%d ", newArr[i]);
        }
        input.close();
    }
}
"""
1 2 3
"""
```

### Search an element in the array usin g"Arrays.binarySearch(arrayName, key)"
```
import java.util.*;
public class Main{
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        
        int[] arr={1,2,3,4,5};
        System.out.println(Arrays.binarySearch(arr, 1)); // 0
        System.out.println(Arrays.binarySearch(arr, 2)); // 1
        System.out.println(Arrays.binarySearch(arr, 3)); // 2
        System.out.println(Arrays.binarySearch(arr, 4)); // 3
        System.out.println(Arrays.binarySearch(arr, 5)); // 4
        input.close();
    }
}
"""
0
1
2
3
4
"""
```
* Arrays.binarySearch will return the "index" of the key value.

### fill an array with a specific value using "Arrays.fill(arrayName, value)";
```
import java.util.*;
public class Main{
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        
        int[] arr={1,2,3,4,5,9};
        
        Arrays.fill(arr, -1);
        for(int i=0; i<arr.length; i++){
            System.out.printf("%d ", arr[i]);
        }
        
        input.close();
    }
}
"""
-1 -1 -1 -1 -1 -1
"""
```

### fill with a specific value for a sepecfic range alone using "Arrays.fill(arrayName, fromIndex(inclusive), toIndex(exclusive), value)"
```
import java.util.*;
public class Main{
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        
        int[] arr={1,2,3,4,5,9};
        
        Arrays.fill(arr, 0, 3, 5);
        for(int i=0; i<arr.length; i++){
            System.out.printf("%d ", arr[i]);
        }
        
        input.close();
    }
}
"""
5 5 5 4 5 9
"""
```

### check whether the 2 one-dimentional arrays are equal or not using "Arrays.equals(arr1, arr2)":
```
import java.util.*;
public class Main{
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        
        int[] arr1={1,2,3,4,5,6};
        int[] arr2={1,-2,4,5};
        
        if(Arrays.equals(arr1, arr2)){
            System.out.printf("Yes\n");
        }
        else{
             System.out.printf("No");
        }
        
        input.close();
    }
}
"""
No
"""
```

### check equal or not for two multi-dimentional arrays using "Arrays.deepEquals(arr1, arr2)":
```
import java.util.*;
public class Main{
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        
        int[][] arr1={ {1,2,3},
                       {4,5,6},
                       {7,8,9} 
                       };
        int[][] arr2={ {1,2,3},
                       {4,5,6},
                       {7,8,9}
                       };
        
        if(Arrays.deepEquals(arr1, arr2)){
            System.out.printf("Yes\n");
        }
        else{
             System.out.printf("No");
        }
        
        input.close();
    }
}
"""
Yes
"""
```

### convert an one-dimentional array to string representation using "Arrays.toString(arrayName)":
```
import java.util.*;
public class Main{
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        
        int[] arr={1,2,3,4,5,6};
        String word=Arrays.toString(arr);
        System.out.printf("%s", word);
        input.close();
    }
}
"""
[1,2,3,4,5,6]
"""
```

### covert an multi-dimentional array to string representation using "Arrays.deepToString(arrayName)":
```
import java.util.*;
public class Main{
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        
        int[][] arr={ {1,2,3},
                      {4,5,6},
                      {7,8,9}
                     };
                     
        String word=Arrays.deepToString(arr);
        System.out.printf("%s", word);
        input.close();
    }
}
"""
[ [1,2,3], [4,5,6], [7,8,9] ]
"""
```

### print all subarrays of an array:
```
import java.util.*;
public class Main {
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        
        int[] arr={1,2,3};
        int n=arr.length;
        for(int i=0; i<n; i++){
            for(int j=i; j<n; j++){
                for(int k=i; k<=j; k++){
                    System.out.printf("%d ", arr[k]);
                }
                 System.out.printf("\n");
            }
        }
        input.close();
    }
}
"""
1
1 2
1 2 3
2
2 3
3
"""
```

### Check if subarray with given product exists in an array
```
import java.util.*;
public class Main {
    public static boolean checkProduct(int[] arr, int n, int target){
        for(int i=0; i<n;i++){
            int product=1;
            for(int j=i; j<n; j++){
                product=product*arr[j];
                if(product==target){
                    return true;
                }
            }
        }
        return false;
    }
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        
        int[] arr={1,2,3,4};
        int n=arr.length;
        int target=12;
        if(checkProduct(arr,n, target)){
            System.out.printf("yes\n");
        }
        else {
             System.out.printf("No\n");
        }
        input.close();
    }
}
"""
yes
"""
```

### merge and sort two arrays
```
import java.util.*;
public class Main{
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        
        int n=input.nextInt();
        int[] arr1=new int[n];
        
        for(int i=0; i<n; i++){
            arr1[i]=input.nextInt();
        }
        
        int m=input.nextInt();
        int[] arr2=new int[m];
        
        for(int i=0; i<m; i++){
            arr2[i]=input.nextInt();
        }
        
        int x=0;
        int[] merged=new int[n+m];
        for(int i=0; i<n; i++){
            merged[x++]=arr1[i];
        }
        for(int i=0; i<m; i++){
            merged[x++]=arr2[i];
        }
    
        Arrays.sort(merged);
        
        for(int i=0; i<x; i++){
            System.out.printf("%d ", merged[i]);
        }
        input.close();
    }
}
"""
4
8 7 9 5
5
3 4 9 7 1
1 3 4 5 7 7 8 9 9
"""
```

### print first duplicate 
```
import java.util.*;
public class Main{
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        
        int n=input.nextInt();
        int[] arr=new int[n];
        
        for(int i=0; i<n; i++){
            arr[i]=input.nextInt();
        }
        boolean found=false;
        for(int i=0; i<n; i++){
            for(int j=i+1; j<n; j++){
                if(arr[i]==arr[j]){
                    found=true;
                    break;
                }
            }
            if(found){
                System.out.printf("%d", arr[i]);
               break;
            }
        }
        
        input.close();
    }
}
"""
6
1 2 3 2 3 4
2
"""
```

### merge and sort k sorted arrays
```
import java.util.*;
public class Main{
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        
        int a=input.nextInt();
        int[] arr1=new int[a];
        
        for(int i=0; i<a; i++){
            arr1[i]=input.nextInt();
        }
        
        int b=input.nextInt();
        int[] arr2=new int[b];
        
        for(int i=0; i<b; i++){
            arr2[i]=input.nextInt();
        }
        
        int c=input.nextInt();
        int[] arr3=new int[c];
        
        for(int i=0; i<a; i++){
            arr3[i]=input.nextInt();
        }
        
        int d=input.nextInt();
        int[] arr4=new int[d];
        
        for(int i=0; i<a; i++){
            arr4[i]=input.nextInt();
        }
        
        int e=input.nextInt();
        int[] arr5=new int[e];
        
        for(int i=0; i<a; i++){
            arr5[i]=input.nextInt();
        }
        
        int x=0;
        int[] merged=new int[a+b+c+d+e];
        
        for(int i=0; i<a; i++){
            merged[x++]=arr1[i];
        }
        
        for(int i=0; i<b; i++){
            merged[x++]=arr2[i];
        }
        
        for(int i=0; i<c; i++){
            merged[x++]=arr3[i];
        }
        
        for(int i=0; i<d; i++){
            merged[x++]=arr4[i];
        }
        
        for(int i=0; i<e; i++){
            merged[x++]=arr5[i];
        }
        
        Arrays.sort(merged);
        
        for(int i=0; i<x; i++){
            System.out.printf("%d ", merged[i]);
        }
        input.close();
        
    }
}
"""
2
4 5
2
7 8
2
1 2
2
0 3
2
10 11
0 1 2 3 4 5 7 8 10 11
"""
```

### Sort Array of 0s, 1s, and 2s:
```
import java.util.*;
public class Main{
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
    
       int n=input.nextInt();
       int[] arr=new int[n];
       
       for(int i=0; i<n; i++){
           arr[i]=input.nextInt();
       }
       
       Arrays.sort(arr);
       
       for(int i=0; i<n; i++){
           System.out.printf("%d ", arr[i]);
       }
        input.close();
        
    }
}
"""
6
2 1 0 1 0 2
0 0 1 1 2 2
"""
```
