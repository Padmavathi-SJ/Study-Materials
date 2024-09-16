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
