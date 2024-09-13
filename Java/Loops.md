### 1. Print the sum of n natural numbers:
```
import java.util.*;
public class Main{
public static void main(String args[]){
    Scanner input=new Scanner(System.in);
    
    int num=input.nextInt();
    int sum=0;
    for(int i=1; i<=num; i++){
        sum+=i;
    }
    System.out.println(sum);
    input.close();
}
}
```
### Print Numbers:
```
import java.util.*;
public class Main{
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        
        int n=input.nextInt();
        for(int i=1; i<=n; i++){
         System.out.print(i+" ");
        }
        input.close();
    }
}
```

### Factorial Calculation:
```
import java.util.*;
public class Main{
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        
        int n=input.nextInt();
        int fact=1;
        for(int i=2; i<=n; i++){
            fact=fact*i;
        }
        System.out.println(fact);
        input.close();
    }
}
"""
5
120
"""
```
