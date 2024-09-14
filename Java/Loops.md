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

### Count Digits in a Number:
```
import java.util.*;
public class Main{
    
    public int countOfDigit(int n){
        int count=0;
        while(n!=0){
            int digit=n%10;
            count++;
            n=n/10;
        }
        return count;
    }

    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        
        int n=input.nextInt();
        
        Main obj=new Main();
        int count=obj.countOfDigit(n);
        
        System.out.println(count);
        input.close();
    }
}
"""
12345
5
"""
```

### Fibonacci Sequence
```
import java.util.*;
public class Main{


    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        
        int n=input.nextInt();
        
        int prev=0;
        System.out.print(prev + " ");
        int curr=1;
        int next;
        for(int i=0; i<n; i++){
            next=prev+curr;
            System.out.print(next + " ");
            prev=curr;
            curr=next;
        }

        input.close();
    }
}
"""
6
0 1 2 3 5 8 13
"""
```

### Prime Numbers: 
```
import java.util.*;
public class Main{
    
    public boolean isPrime(int n){
        if(n<=0){
            return false;
        }
        for(int i=2; i<=n/2; i++){
            if(n%i==0){
                return false;
            }
        }
        return true;
    }


    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        
        int n=input.nextInt();
        
        Main obj=new Main();
        
        for(int i=2; i<n; i++){
            if(obj.isPrime(i)){
                System.out.print(i + " ");
            }
        }

        input.close();
    }
}
"""
25
2, 3, 5, 7, 11, 13, 17, 19, 23
"""
```

### Armstrong Number:
```
import java.util.*;
public class Main{
    
    public boolean isAmstrong(int n){
        int org=n;
        int sum=0;
        while(n!=0){
            int d=n%10;
            sum=sum+(d*d*d);
            n=n/10;
        }
        if(sum==org){
            return true;
        }
        else{
            return false;
        }
    }

    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        
        int n=input.nextInt();
        
        Main obj=new Main();
        if(obj.isAmstrong(n)){
            System.out.println("Yes " + n + " is Amstrong");
        }
        else{
        System.out.println("No");
        }

        input.close();
    }
}
"""
153
Yes 153 is Amstrong
"""
```
### perfect number:
```
import java.util.*;
public class Main{
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        
        int n=input.nextInt();
        
        int sum=0;
        for(int i=1; i<=n/2; i++){
            if(n%i==0){
                sum+=i;
            }
        }
        
        if(sum==n){
            System.out.println(n + " is a perfect number");
        }
        else{
            System.out.println(n + " is not a perfect number");
        }
        
        input.close();
    }
}
```
### Sum of Odd Numbers up to N
```
import java.util.*;
public class Main{
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        
        int n=input.nextInt();
        
        int sum=0;
        for(int i=1; i<=n; i+=2){
            sum+=i;
        }
        System.out.println(sum);
        
        input.close();
    }
}
"""
3
4
"""
```
### Sum of Even Numbers up to N
```
import java.util.*;
public class Main{
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        
        int n=input.nextInt();
        
        int sum=0;
        for(int i=0; i<=n; i+=2){
            sum+=i;
        }
        System.out.println(sum);
        
        input.close();
    }
}
"""
6
12
"""
```

### Find Largest Digit in a Number
```
import java.util.*;
public class Main{
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        
        int n=input.nextInt();
        
        int max=0;
        while(n!=0){
            int digit=n%10;
            if(digit>max){
                max=digit;
            }
            n/=10;
        }
        System.out.println(max);
        
        input.close();
    }
}
"""
458
8
"""
```
### Find Smallest Digit in a Number
```
import java.util.*;
public class Main{
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        
        int n=input.nextInt();
        
        int min=9;
        while(n!=0){
            int digit=n%10;
            if(digit<min){
                min=digit;
            }
            n/=10;
        }
        System.out.println(min);
        
        input.close();
    }
}
"""
546
4
"""
```
### find hcf and lcm of 2 numbers:
```
import java.util.*;
public class Main{
    
    public int findHcf(int n1, int n2){
        while(n2!=0){
            int temp=n2;
            n2=n1%n2;
            n1=temp;
        }
        return n1;
    }
    
    public int findLcm(int n1, int n2, int hcf){
        return (n1*n2)/hcf;
    }
    
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        
        int n1=input.nextInt();
        int n2=input.nextInt();
        
        Main obj=new Main();
        
        int hcf=obj.findHcf(n1, n2);
        int lcm=obj.findLcm(n1, n2, hcf);
        
        System.out.println("HCF of " + n1 + " and " + n2 + " is " + hcf);
        System.out.println("LCM of " + n1 + " and " + n2 + " is " + lcm);
        
        input.close();
    }
}
"""
10
5
HCF of 10 and 5 is 5
LCM of 10 and 5 is 10
"""
```

###  Sum of Series (1 + 1/2 + 1/3 + … + 1/N)
```
import java.util.*;
public class Main{
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        
       int n=input.nextInt();
       
       double sum=0.0;
       for(int i=1; i<=n; i++){
           sum+=1.0/i;
       }
       
       System.out.println(sum);
        input.close();
    }
}
"""
5
2.83333333333
"""
```

### Binary to Decimal Conversion
```
import java.util.*;
public class Main{
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        
       String binary=input.next();
       
       int decimal=Integer.parseInt(binary,2);
       System.out.println(decimal);
        input.close();
    }
}
"""
1010
10
"""
```
### Decimal to Binary Conversion
```
import java.util.*;
public class Main{
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        
       int decimal=input.nextInt();
       String binary=Integer.toBinaryString(decimal);
       
       System.out.println(binary);
        input.close();
    }
}
"""
1010
10
"""
```

###  Find Prime Factors of a Number
```
import java.util.*;
public class Main{
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        
       int n=input.nextInt();
       for(int i=2; i<=n/2; i++){
           if(n%i==0){
               System.out.println(i + " ");
           }
       }
        input.close();
    }
}
"""
10
2
5
"""
```
### Check for Strong Number
```
import java.util.*;
public class Main{
    
    public static int factorial(int n){
        int fact=1;
        for(int i=1; i<=n; i++){
            fact=fact*i;
        }
        return fact;
    }
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        
       int n=input.nextInt();
       int sum=0;
       int orgNum=n;
       while(n!=0){
           int digit=n%10;
           sum+=factorial(digit);
           n/=10;
       }
       
       if(sum==orgNum){
           System.out.println(orgNum + " is a strong number");
       }
       else{
           System.out.println(orgNum + " is not a strong number");
       }
        input.close();
    }
}
"""
145
145 is a strong number
"""
```

###  Perfect Square Check
```
import java.util.*;
public class Main{
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        
       int n=input.nextInt();
       int sqrt=(int) Math.sqrt(n);
       if((sqrt * sqrt)==n){
        System.out.println(n + " is a perfect square");   
       }
       else{
           System.out.println(n + " is not a perfect square");
       }
        input.close();
    }
}
"""
16
16 is a perfect square
"""
```
