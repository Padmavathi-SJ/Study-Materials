### methods



### 1. find the square of any number using the function.
```
#include<stdio.h>
double square(int n){
    return (n*n);
}
int main(){
    int n;
    scanf("%d", &n);
    double sq=square(n);
    printf("%.2f", sq);
    return 0;
}
"""
20
400.00
"""
```

### 2. swap two numbers using a function.
```
#include<stdio.h>
void swap(int *a, int *b){
    int temp;
    temp=*a;
    *a=*b;
    *b=temp;
}
int main() {
    int n1=2, n2=4;
    swap(&n1, &n2);
    printf("n1: %d, n2: %d", n1, n2);
    return 0;
}
"""
n1: 4, n2: 2
"""
```
* while swaping in another function, pass the address of the values, and also swap using their addresses.

### 3.number is even or odd using the function.
```
#include<stdio.h>
#include<string.h>
char* oddOrEven(int n){
    if(n%2==0){
        return "Even";
    }
    else {
        return "Odd";
    }
}

int main() {
    int n=1;
    char result;
    printf("%s", oddOrEven(n));
    return 0;
}
"""
Odd
"""
```

### 4. find the sum of the series 1!/1+2!/2+3!/3+4!/4+5!/5 using the function.
```
#include<stdio.h>
int fact(int n){
    int fact=1;
    while(n!=0){
        fact = fact*n;
        n--;
    }
    return fact;
}

int main() {
    int n=5;
    int sum=0;
    for(int i=1; i<=n; i++){
        int factorial=fact(i);
        factorial=factorial/i;
        sum += factorial;
    }
    printf("%d", sum);
    return 0;
}
"""
34
"""
```

### 5. convert a decimal number to a binary number using the function.
```
#include<stdio.h>
int convert(int n){
    long binaryNum=0;
    int f=1, reminder;
    while(n!=0){
        reminder = n%2;
        binaryNum=binaryNum + reminder * f;
        f=f*10;
        n /= 2;
    }
    return binaryNum;
}
int main() {
    long binaryNum;
    int decimalNum=65;
    binaryNum=convert(decimalNum);
    printf("%ld", binaryNum);
    return 0;
}
"""
1000001
"""
```

### 6. check whether a number is a prime number or not using the function.
```
#include<stdio.h>
int prime(int n){
    if(n<=1){
        return 0;
    }
    for(int i=2; i<n; i++){
        if(n%i==0){
            return 0;
        }
    }
    return 1;
}
int main() {
    int n=10;
    if(prime(n)){
        printf("Yes");
    }
    else{
        printf("No");
    }

    return 0;
}
"""
No
"""
```

### 7. get the largest element of an array using the function:
```
#include<stdio.h>
int largestNum(int arr[], int n){
    int max=arr[0];
    for(int i=1; i<n; i++){
        if(arr[i]>max){
            max=arr[i];
        }
    }
    return max;
}
int main() {
    int arr[]={2,4,8,1,9,5};
    int n=sizeof(arr)/sizeof(arr[0]);
    int result=largestNum(arr, n);
    printf("%d", result);
    return 0;
}
"""
9
"""
```

### 8. check Armstrong and Perfect numbers using the function.
```
#include<stdio.h>
int isAmstrong(int n){
    int orgNum=n;
    int sum=0;
    while(n!=0){
        int rem=n%10;
        sum = sum + (rem*rem*rem);
        n /= 10;
    }
    if(sum == orgNum){
        return 1;
    }
    return 0;
}
int perfectNum(int n){
    int sum=0;
    for(int i=1; i<=n; i++){
        if(n%i==0){
            sum += i;
        }
    }
    if(sum==n){
        return 1;
    }
    return 0;
}
int main() {
    int n=371;
    if(isAmstrong(n)){
        printf("Yes %d is Amstrong\n", n);
    }
    else{
        printf("Yes %d is not an Amstrong\n", n);
    }

    if(perfectNum(n)){
        printf("yes %d is a perfect number\n", n);
    }
    else{
        printf("yes %d is not a perfect number\n", n);
    }
    return 0;
}
"""
Yes 371 is Amstrong
yes 371 is not a perfect number
"""
```
