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
* if the sum of factors of a num is equal to that num itself, that num is a perfect number
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

### Sum of First N Odd Numbers
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
5
9
"""
```

### Sum of First N Even Numbers
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
5
6
"""
```

### Check for Automorphic Number
* Automorphic number is a number whose square ends in the same digits as the number itself.
```
import java.util.*;
public class Main{
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        
       int num=input.nextInt();
       int square=num*num;
       if(String.valueOf(square).endsWith(String.valueOf(num))){
           System.out.println(num + " is an automorphic number");
       }
       else{
           System.out.println(num + " is not an automorphic number");
       }
       input.close();
       }
    }

"""
25
25 is an automorphic number
"""
```

### Find the power of a number:
```
import java.util.*;
public class Main{
    public static void  main(String[] args){
        Scanner input=new Scanner(System.in);
        
        int base=input.nextInt();
        int exponent=input.nextInt();
        int result=1;
        for(int i=1; i<=exponent; i++){
            result = result*base;
        }
        System.out.println(result);
        
    input.close();
    }
}
"""
4
3
81
"""
```
### Prime Numbers Between Two Intervals
```
import java.util.*;
public class Main{
    public static boolean isPrime(int n){
        if(n<=1){
            return false;
        }
        for(int i=2; i<=n/2; i++){
            if(n%i==0){
                return false;
            }
        }
        return true;
    }
    public static void  main(String[] args){
        Scanner input=new Scanner(System.in);
        
        int start=input.nextInt();
        int end=input.nextInt();
        
        for(int i=start; i<=end; i++){
            if(isPrime(i)){
                System.out.print(i + " ");
            }
        }
    input.close();
    }
}
"""
5
13
5 7 11 13
"""
```
### Sum of Prime Numbers up to N
```
import java.util.*;
public class Main{
    public static boolean isPrime(int n){
        if(n<=1){
            return false;
        }
        for(int i=2; i<=n/2; i++){
            if(n%i==0){
                return false;
            }
        }
        return true;
    }
    public static void  main(String[] args){
        Scanner input=new Scanner(System.in);
        
        int n=input.nextInt();
        int sum=0;
        for(int i=0; i<=n; i++){
            if(isPrime(i)){
                sum+=i;
            }
        }
        System.out.println(sum);
    input.close();
    }
}
"""
12
28
"""
```

### Sum of Digits Until Single Digit
```
import java.util.*;
public class Main{
    public static int sumOfDigits(int n){
        int sum=0;
        while(n!=0){
            int digit=n%10;
            sum+=digit;
            n/=10;
        }
        return sum;
    }
    public static void  main(String[] args){
        Scanner input=new Scanner(System.in);
        
        int num=input.nextInt();
        
        while(num>=10){
            num=sumOfDigits(num);
        }
        
        System.out.println(num);
        
    input.close();
    }
}
"""
499
4
"""
```
### Find Cube of a Number
```
import java.util.*;
public class Main{
    public static void  main(String[] args){
        Scanner input=new Scanner(System.in);
        
       int num=input.nextInt();
       int cube=(int) Math.pow(num, 3);
       System.out.println(cube);
        
    input.close();
    }
}
"""
2
8
"""
```
### Find Sum of Cubes of Digits
```
import java.util.*;
public class Main{
    public static void  main(String[] args){
        Scanner input=new Scanner(System.in);
        
       int num=input.nextInt();
       int sum=0;
       while(num!=0){
           int digit=num%10;
           sum+=Math.pow(digit, 3);
           num/=10;
       }
       System.out.println(sum);
        
    input.close();
    }
}
"""
123
36
"""
```
### multiplication table of any number.
```
import java.util.*;
public class Main{
    public static void  main(String[] args){
        Scanner input=new Scanner(System.in);
        
        int n=input.nextInt();
        for(int i=1; i<=10; i++){
            System.out.println(i + " x " + n + " = " + i*n);
        }
    input.close();
    }
}
```
### find first and last digit of a number.
```
import java.util.*;
public class Main{
    public static void  main(String[] args){
        Scanner input=new Scanner(System.in);
        
       int num=input.nextInt();
       int last=num%10;
       int first=num;
       while(first>=10){
               first=first/10;
           }
           
           System.out.printf("first and last are: %d %d", first, last);
        
    input.close();
    }
}
"""
1254
first and last are 1 4
"""
```
### find sum of first and last digit of a number.
```
import java.util.*;
public class Main{
    public static void  main(String[] args){
        Scanner input=new Scanner(System.in);
        
       int num=input.nextInt();
       int last=num%10;
       int first=num;
       while(first>=10){
               first=first/10;
           }
           int sum=first+last;
           System.out.printf("%d", sum);
        
    input.close();
    }
}
"""
458
12
"""
```
### reverse of a number:
```
import java.util.*;
public class Main{
    public static void  main(String[] args){
        Scanner input=new Scanner(System.in);
        
       int num=input.nextInt();
       int rev=0;
       while(num!=0){
           int digit=num%10;
           rev=rev*10+digit;
           num/=10;
       }
      System.out.printf("%d", rev);
        
    input.close();
    }
}
"""
1234
4321
"""
```

### enter a number and print it in words.
```
import java.util.*;
public class Main{
    public static void  main(String[] args){
        Scanner input=new Scanner(System.in);
        
       int num=input.nextInt();
       int rev=0;
       while(num!=0){
           int digit=num%10;
           rev=rev*10+digit;
           num/=10;
       }
      while(rev!=0){
          switch(rev%10){
            case 0:
                  System.out.printf("zero ");
                  break;
            case 1:
                  System.out.printf("one ");
                  break;
            case 2:
                System.out.printf("two ");
                break;
            case 3:
                System.out.printf("three ");
                break;
            case 4:
                System.out.printf("four ");
                break;
            case 5:
                System.out.printf("five ");
                break;
            case 6:
                System.out.printf("six ");
                break;
            case 7:
                System.out.printf("seven ");
                break;
            case 8:
               System.out.printf("eight ");
               break;
            case 9:
                System.out.printf("nine ");
                break;
             
          }
          rev/=10;  
      }
        
    input.close();
    }
}
"""
1234
one two three four
"""
```
### find power of a number
```
import java.util.*;
public class Main{
    public static void  main(String[] args){
        Scanner input=new Scanner(System.in);
        
       int base=input.nextInt();
       int exponent=input.nextInt();
       
       int power=(int) Math.pow(base, exponent);
       System.out.printf("%d ^ %d = %d", base, exponent, power);
    input.close();
    }
}
"""
2
5
2 ^ 5 = 32
"""
```

### find power of a number using for loop.(without using Math.pow function)
```
import java.util.*;
public class Main{
    public static void  main(String[] args){
        Scanner input=new Scanner(System.in);
        
       int base=input.nextInt();
       int exponent=input.nextInt();
       
       int power=1;
       for(int i=1; i<=exponent; i++){
           power=power*base;
       }
       System.out.printf("%d",power);
    input.close();
    }
}
"""
2
5
32
"""
```

### find all factors of a number
```
import java.util.*;
public class Main{
    public static void  main(String[] args){
        Scanner input=new Scanner(System.in);
        
       int n=input.nextInt();
       
       for(int i=1; i<=n; i++){
           if(n%i==0){
               System.out.printf("%d ", i);
           }
       }
    input.close();
    }
}
"""
12
1 2 3 4 6 12
"""
```
### print all Strong numbers between 1 to n.
```
import java.util.*;
public class Main{
    public static int factorial(int n){
        int fact=1;
        for(int i=2; i<=n; i++){
            fact=fact*i;
        }
        return fact;
    }
    public static boolean isStrong(int n){
        int orgNum=n;
        int sum=0;
        while(n!=0){
            int digit=n%10;
            sum+=factorial(digit);
            n/=10;
        }
        if(sum==orgNum){
            return true;
        }
        else{
            return false;
        }
    }
    
    public static void  main(String[] args){
        Scanner input=new Scanner(System.in);
        
        int n=input.nextInt();
        for(int i=0; i<n; i++){
            if(isStrong(i)){
                System.out.printf("%d ", i);
            }
        }
    input.close();
    }
}
"""
15
0 1 2
"""
```
## Patterns
### pattern - 01
```
import java.util.*;
public class Main{
    public static void  main(String[] args){
        Scanner input=new Scanner(System.in);
        
        int r=input.nextInt();
       // int c=input.nextInt();
        
        for(int i=1; i<=r; i++){
            for(int j=0; j<i; j++){
                System.out.printf("%d ", i+j);
            }
            System.out.printf("\n");
        }
        
    input.close();
    }
}
"""
5
1
2 3
3 4 5
4 5 6 7
5 6 7 8 9
"""
```

### pattern -02(reverse of pattern 1):
```
import java.util.*;
public class Main{
    public static void  main(String[] args){
        Scanner input=new Scanner(System.in);
        
        int r=input.nextInt();
       // int c=input.nextInt();
        
        for(int i=r; i>=1; i--){
            for(int j=0; j<i; j++){
                System.out.printf("%d ", i+j);
            }
            System.out.printf("\n");
        }
        
    input.close();
    }
}
"""
5
5 6 7 8 9
4 5 6 7
3 4 5
2 3
1
"""
```

### pattern-03
```
import java.util.*;
public class Main{
    public static void  main(String[] args){
        Scanner input=new Scanner(System.in);
        
        int r=input.nextInt();
       // int c=input.nextInt();
        
        for(int i=1; i<=r; i++){
            for(int j=1; j<=i; j++){
                System.out.printf("%d ", j*5);
            }
            System.out.printf("\n");
        }
        
    input.close();
    }
}
"""
5
5
5 10
5 10 15
5 10 15 20
5 10 15 20 25
"""
```
