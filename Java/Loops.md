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

### Reverse a Number: 
```
import java.util.*;
public class Main{
    
    public int reverse(int n){
        int rev=0;
        
        while(n!=0){
        int digit=n%10;
        rev=rev*10+digit;
        n=n/10;
        }
        return rev;
    }
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        
        int n=input.nextInt();
        
        Main obj=new Main();
        int reversed=obj.reverse(n);
        
        System.out.println(reversed);
        
        input.close();
    }
}

"""
12345
54321
"""
```

### Sum of digits:
```
import java.util.*;
public class Main{
    
    public int sumOfDigit(int n){
        int sum=0;
        while(n!=0){
            int digit=n%10;
            sum+=digit;
            n=n/10;
        }
        return sum;
    }

    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        
        int n=input.nextInt();
        
        Main obj=new Main();
        int sum=obj.sumOfDigit(n);
        
        System.out.println(sum);
        input.close();
    }
}

"""
12345
15
"""
```
