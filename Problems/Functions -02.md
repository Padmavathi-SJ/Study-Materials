### methods
* All problems will be done by using functions only, if needed some other methods also used


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

### 9. print all perfect numbers in a given range using the function.
```
#include<stdio.h>
int isPerfect(int n){
    int sum=0;
    for(int i=1; i<=n/2; i++){
        if(n%i==0){
            sum += i;
        }
    }
    if(sum==n){
        return 1;
    }
    return 0;
}
void findPerfectNum(int start, int end){
    for(int i=start; i<=end; i++){
        if(isPerfect(i)){
            printf("%d ", i);
        }
    }
}
int main() {
    int start=1;
    int end=100;
    findPerfectNum(start, end);
    return 0;
}
"""
6 28
"""
```

### 10. check whether two given strings are an anagram.
```
#include<stdio.h>
#include<string.h>
#include<stdlib.h>
int areAnagrams(char str1[], char str2[]){
    if(strlen(str1)!=strlen(str2)){
        return 0;
    }
    int count1[256]={0};
    int count2[256]={0};
    int l1=strlen(str1);
    for(int i=0; i<l1; i++){
        count1[str1[i]]++;
    }
    int l2=strlen(str2);
    for(int i=0; i<l2; i++){
        count2[str2[i]]++;
    }
    for(int i=0; i<256; i++){
        if(count1[i]!=count2[i]){
            return 0;
        }
    }
    return 1;
}
int main() {
    char str1[100]="spare";
    char str2[100]="pears";
    if(areAnagrams(str1, str2)){
        printf("yes Anagrams\n");
    }
    else{
        printf("Not Anagrams\n");
    }
    return 0;
}
"""
yes Anagrams
"""
```

### 11. In a 2D array find, non zero sum, sum_max_row, sum_max_col, totalSum
```
#include<stdio.h>
int main(){
    int rows=3;
    int cols=3;
    int matrix[rows][cols];
    for(int i=0; i<rows; i++){
        for(int j=0; j<cols; j++){
            scanf("%d", &matrix[i][j]);
        }
    }
    int sum_max_row=0;
    int sum_max_cols=0;
    int sum_non_zero=0;
    int totalSum=0;
    
    for(int i=0; i<rows; i++){
        for(int j=0; j<cols; j++){
            if(matrix[i][j] != 0){
                sum_non_zero += matrix[i][j];
            }
        }
    }
    
    for(int i=0; i<rows; i++){
        int max_in_row=matrix[i][0];
        for(int j=1; j<cols; j++){
            if(matrix[i][j] > max_in_row){
                max_in_row=matrix[i][j];
            }
        }
        sum_max_row += max_in_row;
    }
    
    for(int j=0; j<cols; j++){
        int max_in_col=matrix[0][j];
        for(int i=1; i<rows; i++){
            if(matrix[i][j] > max_in_col){
                max_in_col=matrix[i][j];
            }
        }
        sum_max_cols += max_in_col;
    }
    
    totalSum += sum_non_zero + sum_max_row + sum_max_cols;
    
    printf("Sum of non_zero: %d\n", sum_non_zero);
    printf("Sum of sum_max_row: %d\n", sum_max_row);
    printf("Sum of sum_max_cols: %d\n", sum_max_cols);
    printf("Sum of totalSum: %d\n", totalSum);
    return 0;
    }
"""
1 2 34
4 5 6
7 8 9
Sum of non_zero: 45
Sum of sum_max_row: 18
Sum of sum_max_cols: 24
Sum of totalSum: 87
"""
```

### 12. change frst vowel in the string to the frst consonant in the string ,scnd vowel to scnd  consonant
```
#include<stdio.h>
#include<string.h>
#include<ctype.h>
void main(){
    char str[256];
    fgets(str, 256, stdin);
    str[strcspn(str, "\n")]='\0';
    char vowels[5]={'a', 'e', 'i', 'o', 'u'};
    for(int i=0; i<strlen(str); i++){
        str[i] =tolower(str[i]);
        for(int j=0; j<5; j++){
        if(str[i] == vowels[j]){
            str[i] = vowels[(j+1)%5];
            break;
        }
        }
    }
    char consonants[21] = {
    'b', 'c', 'd', 'f', 'g', 'h', 'j', 'k', 'l', 'm', 
    'n', 'p', 'q', 'r', 's', 't', 'v', 'w', 'x', 'y', 'z'};
    for(int i=0; i<strlen(str); i++){
        str[i]=tolower(str[i]);
        for(int j=0; j<21; j++){
            if(str[i] == consonants[j]){
                str[i]=consonants[(j+1)%21];
                break;
            }
        }
    }
printf("%s", str);
}
"""
Padmavathi
qefnewevjo
"""
```

### 13. change frst consonant in the string to the frst vowel int the string ,scnd consonant to scnd  vowel
```
#include<stdio.h>
#include<string.h>
#include<ctype.h>
void main(){
    char str[256];
    fgets(str, 256, stdin);
    str[strcspn(str, "\n")]='\0';
    char vowels[5]={'a', 'e', 'i', 'o', 'u'};

    char consonants[21] = {
    'b', 'c', 'd', 'f', 'g', 'h', 'j', 'k', 'l', 'm', 
    'n', 'p', 'q', 'r', 's', 't', 'v', 'w', 'x', 'y', 'z'};
    int index=0;
    for(int i=0; i<strlen(str); i++){
        str[i]=tolower(str[i]);
        for(int j=0; j<21; j++){
            if(str[i] == consonants[j]){
                str[i]=vowels[index%5];
                index++;
                break;
            }
        }
    }
printf("%s", str);
}
"""
padmavathi
aaeiaoauai
"""
```
