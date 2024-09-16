### print statement:
```
public class Hello {
    public static void main(String[] arg){
        System.out.println("Hello mummy");
        System.out.println("Good morning");
    }
}
```
output: Hello mummy
        Good morning

### add two integers:
```
public class Hello {
    public static void main(String[] arg){
        int a=10;
        int b=90;
        int sum=a+b;
        System.out.println("The sum is:" + sum);
    }
}
```
output: The sum is: 100

### Getting input from user:
```
import java.util.Scanner;

public class Hello{
    public static void main(String[] args){
        //creating a scanner object to read input
        Scanner input = new Scanner(System.in);
        //input=object name
        //Scanner = class name
        System.out.print("Enter the num1: ");
        int num1=input.nextInt();
      //nextInt(): This is a method of the Scanner class. When called, it waits for the user to enter an integer value,
      reads that value, and then returns it as an int data type.
        
        System.out.print("Enter the num2: ");
        int num2=input.nextInt();
        
        int sum=num1+num2;
        
        System.out.println("The sum is: " + sum);
        
       // input.close();
    }
}
```

### Check if a Number is Even or Odd
```
import java.util.Scanner;

public class OddorEven{
    public static void main(String[] arg){
        Scanner input = new Scanner(System.in);
        
        System.out.print("Enter a num: ");
        int num=input.nextInt();
        
        if(num%2==0){
            System.out.println(num + "is even");
        }
        else{
            System.out.println(num + "is odd");
        }
        input.close();
    }
}
```
### Find the Largest of Three Numbers
```
import java.util.Scanner;

public class largest{
    public static void main(String[] arg){
        Scanner input = new Scanner(System.in);
        
        System.out.print("Enter a num1: ");
        int num1=input.nextInt();
        
        System.out.print("Enter a num2: ");
        int num2=input.nextInt();
        
        System.out.print("Enter a num3: ");
        int num3=input.nextInt();
        int maxnum;
        if(num1>=num2 && num1>=num3){
            maxnum=num1;
        }
        else if(num2>=num1 && num2>=num3){
            maxnum=num2;
        }
        else{
            maxnum=num3;
        }
        
        System.out.println("The largest num: " + maxnum);
        input.close();
    }
}
```
### Check if a Number is Positive, Negative, or Zero
```
import java.util.Scanner;

public class find{
    public static void main(String[] arg){
        Scanner input = new Scanner(System.in);
        
        System.out.print("Enter a num: ");
        int num=input.nextInt();
        
        if(num>0){
            System.out.println("The num is positive");
        }
        else if(num<0){
            System.out.println("The num is negative");
        }
        else {
            System.out.println("The num is zero");
        }
        input.close();
    }
}
```
### Check for Leap Year
```
import java.util.Scanner;

public class find{
    public static void main(String[] arg){
        Scanner input = new Scanner(System.in);
        
        System.out.print("Enter a year: ");
        int year=input.nextInt();
        
        if((year%4==0 && year%100!=0) || (year%400==0)) {
            System.out.println("Leap year");
        }
        else{
            System.out.println("Not");
        }
        input.close();
    }
}
```
### Get and Print Different Types of Data:
```
import java.util.Scanner;

public class seperate{
    public static void main(String[] arg){
        Scanner input = new Scanner(System.in);
        
        System.out.print("enter a num: ");
        int num=input.nextInt();
        
        System.out.print("enter a char: ");
        char letter=input.next().charAt(0);
        
        input.nextLine();
        
        System.out.print("enter a string: ");
        String word=input.nextLine();
        
        System.out.print("enter a size of array: ");
        int arrSize=input.nextInt();
        
        System.out.print("enter tha array elements: ");
        int[] arr=new int[arrSize];
        
        for(int i=0; i<arrSize; i++){
            arr[i]=input.nextInt();
        }
        System.out.println("num is: " + num);
        
        System.out.println("char is: " + letter);
        
        System.out.println("string is: " + word);
        
        System.out.print("Array: ");
        for(int i:arr) {
            System.out.print(i + " ");
        }
        
        System.out.println();
        
        input.close();
    }
}
```

### Get and Print Different Types of Data:
```
import java.util.Scanner;

public class find{
    public static void main(String[] arg){
        Scanner input = new Scanner(System.in);
        
        int num=input.nextInt();
        
        char letter=input.next().charAt(0);
        
        String word=input.next();
        
        int arrSize=input.nextInt();
        int[] arr=new int[arrSize];
        for(int i=0; i<arrSize; i++){
            arr[i]=input.nextInt();
        }
        
        System.out.println("the nums is: " + num);
        
        System.out.println("the char is: " + letter);
        
        System.out.println("The word is: " + word);
        
        System.out.print("the array: ");
        for(int i:arr){
            System.out.print(i+" ");
        }
        
        input.close();
    }
}
```
### Check Char is vowel or constant or invalid char:
```
import java.util.Scanner;

public class Main{
    public static void main(String[] arg){
        Scanner input = new Scanner(System.in);
        
        char letter=input.next().toLowerCase().charAt(0);
        
        if(letter=='a' || letter=='e' || letter=='i' || 
        letter=='o' || letter=='u'){
            System.out.println("vowel");
        }
        else if(letter>='a' && letter<='z'){
            System.out.println("Constant");
        }
        
        else{
            System.out.println("Not valid");
        }
        input.close();
    }
}
```

### Grade allocation:
```
import java.util.Scanner;
    public class Main{
        public static void main(String[] arg){
            Scanner input=new Scanner(System.in);
            
            System.out.print("Enter you mark: ");
            int mark=input.nextInt();
            
            if(mark>=90){
                System.out.println("A");
            }
            else if(mark>=80 && mark<=89){
                System.out.println("B");
            }
            else if(mark>=70 && mark<=79){
                System.out.println("C");
            }
            else if(mark>=60 && mark<=69){
                System.out.println("D");
            }
            else {
                System.out.print("F");
            }
        
        input.close();
        }
    }
```

### Check for Voting Eligibility:
```
import java.util.Scanner;

public class Main{
    public static void main(String[] arg){
        Scanner input=new Scanner(System.in);
        
        System.out.print("Enter your age: ");
        int age=input.nextInt();
        
        if(age>=18){
            System.out.println("Eligible");
        }
        else{
            System.out.print("Not eligible");
        }
        input.close();
    }
}
```

### Simple Calculator:
```
import java.util.Scanner;

public class Main{
    public static void main(String[] arg){
        Scanner input=new Scanner(System.in);
        
        double num1=input.nextDouble();
        double num2=input.nextDouble();
        
        char operator= input.next().charAt(0);
        
        double result;
        switch(operator) {
            case '+':
                result=num1+num2;
                System.out.println(result);
                break;
                
            case '-':
                result=num1-num2;
                System.out.println(result);
                break;
            
            case '*':
                result=num1*num2;
                System.out.println(result);
                break;
                
            case '/':
                result=num1/num2;
                System.out.println(result);
                break;
        }
        input.close();
        
    }
}
```

### CHeck less than 10 -> small, between 10 to 100 -> medium, above 100 -> large:
```
import java.util.Scanner;

public class Main{
    public static void main(String[] arg){
        Scanner input=new Scanner(System.in);
        
        int num = input.nextInt();
        
        if(num<=10){
            System.out.println("Small");
        }
        else if(num>=10 && num<=100){
            System.out.println("Medium");
        }
        else if(num>=100){
            System.out.println("Large");
        }
        else{
            System.out.print("Not valid");
        }
        
        input.close();
        
    }
}
```

### alculate the Discount Based on Purchase Amount
**Write a program that calculates the discount on a purchase based on the total amount spent. The discount rates are as follows:
More than $500: 20% discount
$200 to $500: 10% discount
$100 to $200: 5% discount
$100 or less: No discount.**

```
import java.util.Scanner;

public class Main{
    public static void main(String[] arg){
        Scanner input=new Scanner(System.in);
        
        int amount=input.nextInt();
        double discount;
        double discountedAmount=0;
        if(amount>500){
            discount=0.20;
        }
        else if(amount>=200 && amount<=500){
            discount=0.10;
        }
        else if(amount>=100 && amount<=200){
            discount=0.05;
        }
        else{
            discount=0.00;
        }
        
        discountedAmount= amount-(amount*discount);
        System.out.println("%.2f",discountedAmount);
        input.close();
        
    }
}
```
output: 450
        450.00


```
import java.util.Scanner;

public class Main{
    public static void main(String[] arg){
        Scanner input=new Scanner(System.in);
        
        int amount=input.nextInt();
        double discount;
        int discountedAmount=0;
        if(amount>500){
            discount=0.20;
        }
        else if(amount>=200 && amount<=500){
            discount=0.10;
        }
        else if(amount>=100 && amount<=200){
            discount=0.05;
        }
        else{
            discount=0.00;
        }
        
        discountedAmount=int (amount-(amount*discount));
        System.out.println(discountedAmount);
        input.close();
        
    }
}
```
output: 450
        450


###  Find the Second Largest Number Among Four:

```
import java.util.Scanner;

public class Main{
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter four numbers: ");
        int num1 = scanner.nextInt();
        int num2 = scanner.nextInt();
        int num3 = scanner.nextInt();
        int num4 = scanner.nextInt();
        
        int largest=Math.max(Math.max(num1, num2), Math.max(num3, num4));
        int secondLargest=Integer.MIN_VALUE;
        if(num1!=largest){
            secondLargest=Math.max(secondLargest, num1);
            secondLargest=num1;
        }
        if(num2!=largest){
            secondLargest=Math.max(secondLargest, num2);
            secondLargest=num2;
        }
        if(num3!=largest){
            secondLargest=Math.max(secondLargest, num3);
            secondLargest=num3;
        }
        if(num4!=largest){
            secondLargest=Math.max(secondLargest, num4);
            secondLargest=num4;
        }
        System.out.print(secondLargest);

        
        scanner.close();
    }
}
```

### Check for traingle type:
```
import java.util.Scanner;

public class Main{
    public static void main(String[] arg){
        Scanner input=new Scanner(System.in);
        
        int side1=input.nextInt();
        int side2=input.nextInt();
        int side3=input.nextInt();
        
        if(side1+side2>side3 && side2+side3>side1 && side1+side3>side2){
        if(side1==side2 && side2==side3){
            System.out.println("Equilateral");
        }
        else if(side1==side2 || side2==side3 || side3==side1){
            System.out.println("Isosceles");
        }
        else {
            System.out.println("Scalene");
        }
        }
        else{
            System.out.println("Invalid data");
        }
        input.close();
    }
}
```

### Find second largest from among 3:
```
import java.util.Scanner;

public class Main{
    public static void main(String[] arg){
        Scanner input=new Scanner(System.in);
        
        int num1=input.nextInt();
        int num2=input.nextInt();
        int num3=input.nextInt();
        
        int max=Math.max(num1, Math.max(num2, num3));
        int max2=Integer.MIN_VALUE;
        
        if(num1!=max){
            max2=Math.max(max2, num1);
        }
        if(num2!=max){
            max2=Math.max(max2, num2);
        }
        if(num3!=max){
            max2=Math.max(max2, num3);
        }
        
        System.out.println(max2);
        input.close();
    }
}
```

### get and print different types of data:
```
import java.util.Scanner;
public class Main{
    public static void main(String[] args){
        Scanner num1=new Scanner(System.in);
       
        int i=num1.nextInt();
        double d=num1.nextDouble();
        float f=num1.nextFloat();
        num1.nextLine();//to clear newline char left by nextFloat
        char c=num1.next().charAt(2);
        num1.nextLine();//to clear newline char left by charAt
        String s=num1.nextLine();
        boolean b=num1.nextBoolean();
        long l=num1.nextLong();
        short st=num1.nextShort();
        
        System.out.println("Integer"+" "+i);
        System.out.println("double:"+d);
        System.out.println("float"+f);
        System.out.println("char"+c);
        System.out.println("string"+s);
        System.out.println("boolean"+b);
        System.out.println("long"+l);
        System.out.println("short"+st);
        
    }
}
```

### positive & negative
```
import java.util.Scanner;
import static java.lang.Math.sqrt;
public class Main{
    public static void main(String[] arg){
        Scanner input=new Scanner(System.in);
        
        int num=input.nextInt();
        
        if(num<0){
            if(Math.abs(num)<1){
               System.out.println("num " + num + " is Negative & small");
            }
            else if(Math.abs(num)>1000000){
               System.out.println("num " + num + " is Negative & greater");

            }
            else{
                System.out.println("num " + num + " is Negative");
            }
        }
        
        else if(num>0){
            if(num<1){
                System.out.println("num " + num + " is Positive & small");
            }
            else if(num>1000000){
                System.out.println("num " + num + " is Positive & greater");
            }
            else{
                System.out.println("num " + num + " is Positive");
            }
        }
        
        else{
            System.out.println("num " + " " + num  + "is zero");
        }
        
       
        input.close();
    }
}
```

### num of days in a month of year
```
import java.util.Scanner;
import static java.lang.Math.sqrt;
public class Main{
    public static void main(String[] arg){
        Scanner input=new Scanner(System.in);
        
        int m=input.nextInt();
        int y=input.nextInt();
        if(m>=1 && m<=12){
            if(m==1 || m==3 || m==5 || m==7 || m==9 || m==11){
                System.out.println("month " + m + " has 31 days");
            }
            else if(m==4 || m==6 || m==8 || m==10 || m==12){
                System.out.println("month " + m + " has 30 days");
            }
            else if(m==2){
                if((y%4==0 && y%100!=0) || (y%400==0)){
                    System.out.println("month " + m + " has 29 days");
                }
                else{
                    System.out.println("month " + m + " has 28 days");
                }
            }
        }
        else{
            System.out.println("invalid month input");
        }
        input.close();
    }
}
```

### avg and sum
```
import java.util.Scanner;

class Main{
    public static void main(String[] args) {
        Scanner input=new Scanner(System.in);
        int num=input.nextInt();
        int sum=0;
        for(int i=1;i<=num;i++){
            System.out.println(i);
            sum+=i;
        }
        float avg=sum/num;
        System.out.println(sum);
        System.out.println(avg);
    }
}
```
### print 2 decimal alone
```
import java.util.Scanner;
public class Main{
    public static void main(String[] arg){
        Scanner input=new Scanner(System.in);
        float num=input.nextFloat();
        System.out.printf("Value is %.2f\n", num);
        input.close();
    }
}

(or)

import java.util.Scanner;
public class Main{
    public static void main(String[] arg){
        Scanner input=new Scanner(System.in);
        double num=input.nextDouble();
        System.out.printf("Value is %.2f\n", num);
        input.close();
    }
}
```

### find slope 
```
import java.util.Scanner;

public class Main {
    public static void main(String[] arg) {
        Scanner input = new Scanner(System.in);

        float x1 = input.nextFloat();
        float x2 = input.nextFloat();
        float y1 = input.nextFloat();
        float y2 = input.nextFloat();

        // Check if the denominator is 0, indicating a vertical line
        if (x2 - x1 == 0) {
            System.out.println("Vertical Line");
        } else {
            float slope = (y2 - y1) / (x2 - x1);

            if (slope > 0) {
                System.out.println("Positive Line");
            } else if (slope < 0) {
                System.out.println("Negative Line");
            } else {
                System.out.println("Horizontal Line");
            }
        }
        
        input.close();
    }
}
```

### Find compound interest:
```
import java.util.*;

class Main{
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        
        int p=input.nextInt();
        double r=input.nextDouble();
        int t=input.nextInt();
        int n=input.nextInt();
        double m1= Math.pow(1+ (r/n), n*t);
        double A=p * m1;
        System.out.printf("%.2f", A);
        input.close();
    }
}
```
### Temperature conversion:
```
import java.util.*;

class Main{
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        
        double F=input.nextDouble();
        double C=input.nextDouble();
        double Faren=((9.0/5.0)*C) + 32.0;
        double Celcius=(5.0/9.0) * (F - 32.0);
        
        System.out.printf("%.2f\n", Faren);
        System.out.printf("%.2f", Celcius);
        input.close();
    }
}
```
### finding the quadrtic Equation:
```
import java.util.*;

class Main{
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        
        int a=input.nextInt();
        int b=input.nextInt();
        int c=input.nextInt();
        if(a==0){
            System.out.println("This equation has no roots");
        }
        else {
        double x=(b*b) - (4*a*c);
        if(x<0){
            System.out.println("this equation has complex roots");
        }
        else {
            double y=Math.sqrt(x);
        double root1= (-b + y) / (2*a);
        double root2= (-b - y) / (2*a);
        
        System.out.printf("%.2f\n", root1);
        System.out.printf("%.2f", root2);
        }
        }
        input.close();
    }
}
```
## Math functions:
### Math.floor function -- to rounding down the floating-point values in a loop:
```
import java.util.*;
public class Main{
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        
    for (double i = 1.5; i <= 5.5; i += 1.0) {
    System.out.println(Math.floor(i));  
}

        input.close();
    }
}
"""
1.0
2.0
3.0
4.0
5.0
"""
```

### Math.ceil function --- rounding down the floating point value:
```
import java.util.*;
public class Main{
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        
    for (double i = 1; i <= 5; i += 1) {
    System.out.println(Math.ceil(i));  
}

        input.close();
    }
}
"""
1.0
2.0
3.0
4.0
5.0
"""
```

### Math.floor function:
```
import java.util.*;
public class Main{
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        
    double a=2.645235;
    System.out.println((int) Math.floor(a));

        input.close();
    }
}
"""
2.645235
2
"""
```

### Math.ceil function:
```
import java.util.*;
public class Main{
    public static void main(String[] args){
        Scanner input=new Scanner(System.in);
        
    double a=2.145235;
    System.out.println((int)Math.ceil(a));

        input.close();
    }
}
"""
3
"""
```
