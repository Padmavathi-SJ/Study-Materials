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
