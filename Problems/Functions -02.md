### methods
* All problems will be done by using functions only, if needed some other methods also used
* for storing characters in a new string in c ---> have to **allocate memory first** as --> __char *temp = (char) malloc ((lenth of the predefined string + 1) * sizeof(char));__ --> after using this temp string then free the allocated memory for temp as **free(temp)**
* for copying in a new string no need to allocate memory, but have to define the size of the new string as **char temp[100]**


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

###
```
#include<stdio.h>
#include<stdbool.h>
bool isPeak(int matrix[100][100], int i, int j, int rows, int cols){
    int left= j>0 ? matrix[i][j-1] : -1; //left
    int right= j<cols-1 ? matrix[i][j+1]: -1; //right
    int up= i>0 ? matrix[i-1][j] : -1; //up
    int down= i<rows-1 ? matrix[i+1][j] : -1; //down
    
    return matrix[i][j] > left && matrix[i][j] > right &&
           matrix[i][j] > up && matrix[i][j] > down;
}
void main(){
    int rows=3;
    int cols=3;
    int matrix[rows][cols];
    for(int i=0; i<rows; i++){
        for(int j=0; j<cols; j++){
            scanf("%d", &matrix[i][j]);
        }
    }
    int peakElement=matrix[0][0];
    int found=0;
    for(int i=0; i<rows; i++){
        for(int j=0; j<cols; j++){
            if(isPeak(matrix, i, j, rows, cols)){
               if(matrix[i][j] > peakElement){
                   peakElement=matrix[i][j];
               }
            }
        }
    }
    printf("peak element is: %d", peakElement);
    
}
"""
1 2 3
4 5 6
7 8 9
p --> Peak Element
"""
```
### Check whether good number or not:
```
#include<stdio.h>
#include<stdbool.h>
#include<string.h>
bool check(int num){
    if(num<=1){
        return false;
    }
    for(int i=2; i*i<=num; i++){
        if(num%i==0){
            return false;
        }
    }
    return true;
}
int main() {
    char num[256];
    fgets(num, 256, stdin);
    num[strcspn(num, "\n")]='\0';
    int found=1;
    for(int i=0; i<strlen(num); i++){
        int digit=num[i]-'0';
        if(i%2==0){
            if(digit%2==0){
                found=1;
            }
            else{
                found=0;
                break;
            }
        }
        else {
            if(check(digit)){
                found=1;
            }
            else{
                found=0;
                break;
            }
        }
    }
    if(found){
        printf("Yes\n");
    }
    else{
        printf("No\n");
    }
    return 0;
}
"""
num=2545
Yes (good number)
"""
```

### permutation
* n!/n!-r!
```
#include<stdio.h>
int factorial(int n){
    if(n==1 || n==0) return 1;
    return n*factorial(n-1);
}
int main(){
    int n1;
    int n2;
    scanf("%d", &n1);
    scanf("%d", &n2);
    int result=factorial(n1)/factorial(n1-n2);
    printf("%d", result);
    return 0;
}
"""
5
4
120
"""
```

### permutation of a string
```
#include<stdio.h>
#include<string.h>
#include<math.h>
int factorial(int n){
    if(n==1 || n==0) return 1;
    return n*factorial(n-1);
}
int main(){
    char str[256];
    fgets(str, 256, stdin);
    str[strcspn(str, "\n")]='\0';
    int l=strlen(str);
    int freq[100];
    int index=0;
    for(int i=0; i<l; i++){
        int count=1;
        if(str[i]!='\0'){
        for(int j=i+1; j<l; j++){
            if(str[i]==str[j]){
                count++;
            }
        }
        freq[index++]=count;
        }
    }
    int denominator=1;
    for(int i=0; i<index; i++){
        denominator *= factorial(freq[i]);
    }
     int result=factorial(l)/denominator;
     printf("%d", result);
    return 0;
}
"""
LEVEL
30 // 5!/2!*2!
"""
```

### circular permutation
```
#include<stdio.h>
#include<math.h>
int factorial(int n){
    if (n==0 || n==1) return 1;
    return n*factorial(n-1);
}
int main(){
    int n;
    scanf("%d",&n);
    int result=factorial(n-1);
    printf("%d", result);
}
"""
6 //n
120 //n-1
"""
```

### palindromic substring
```
#include<stdio.h>
#include<string.h>
#include<stdbool.h>

bool check(char str[], int left, int right){
    while(left<right){
        if(str[left]!=str[right]){
            return false;
        }
        left++;
        right--;
    }
    return true;
}
int main(){
    char str[256];
    fgets(str, 256, stdin);
    str[strcspn(str, "\n")]='\0';
    int longestLength=0;
    int l=strlen(str);
    int startIndex=0;
    for(int i=0; i<l; i++){
       for(int j=i; j<l; j++){
           if(check(str, i, j)){
               int len=j-i+1;
               if(len>longestLength){
                   longestLength=len;
                   startIndex=i;
               }
           }
       }
    }
    for(int i=startIndex; i<startIndex+longestLength; i++){
        printf("%c", str[i]);
    }
    printf("\n");
    printf("%d", longestLength);
}
"""
padmadamvathi
madam //palindromic substring
5 //length of palndromic string
"""
```

### Palindromic substring
```
#include<stdio.h>
#include<string.h>
#include<stdbool.h>

bool check(char str[], int left, int right){
    while(left<right){
        if(str[left]!=str[right]){
            return false;
        }
        left++;
        right--;
    }
    return true;
}
int main(){
    char str[256];
    fgets(str, 256, stdin);
    str[strcspn(str, "\n")]='\0';
    int longestLength=0;
    int l=strlen(str);
    int startIndex=0;
    for(int i=0; i<l; i++){
       for(int j=i; j<l; j++){
           if(check(str, i, j)){
               int len=j-i+1;
               if(len>longestLength){
                   longestLength=len;
                   startIndex=i;
               }
           }
       }
    }
    for(int i=startIndex; i<startIndex+longestLength; i++){
        printf("%c", str[i]);
    }
    printf("\n");
    printf("%d", longestLength);
}
"""
padmadammathi
madam
5
"""
```

### Circular Prime
```
#include<stdio.h>
#include<math.h>
#include<stdbool.h>
bool prime(int num){
    if(num<=1){
        return false;
    }
    for(int i=2; i*i<=num; i++){
        if(num%i==0){
            return false;
        }
    }
    return true;
}
int numOfDigits(int num){
    int count=0;
    while(num!=0){
        count++;
        num/=10;
    }
    return count;
}
int rotateNum(int num, int digits){
    int rem=num%10;
    int quo=num/10;
    int shift=pow(10, digits-1);
    
    return rem*shift+quo;
}
bool circularPrimeHelper(int currNum, int org, int digits){
    if(currNum == org){
        return true;
    }
    if(!prime(currNum)){
        return false;
    }
    int rotated=rotateNum(currNum, digits);
    return circularPrimeHelper(rotated, org, digits);
}
bool circularPrime(int num){
    if(!prime(num)){
        return false;
    }
    int digits=numOfDigits(num);
    int rotated=rotateNum(num, digits);
    return circularPrimeHelper(rotated, num, digits);
}
int main(){
    int num;
    scanf("%d", &num);
    if(circularPrime(num)){
        printf("Yes\n");
    }
    else{
        printf("No\n");
    }
    return 0;
}
"""
197
yes
"""
```
### printf first occurance of anagrams
```
#include<stdio.h>
#include<string.h>
#include<stdbool.h>
#include<ctype.h>
bool areAnagrams(char str1[], char str2[]){
    if(strlen(str1)!=strlen(str2)){
        return false;
    }
    int count1[256]={0};
    int count2[256]={0};
    
    for(int i=0; i<strlen(str1); i++){
        count1[str1[i]]++;
    }
    
    for(int i=0; i<strlen(str2); i++){
        count2[str2[i]]++;
    }
    
    for(int i=0; i<256; i++){
        if(count1[i] != count2[i]){
            return false;
        }
    }
    return true;
}

int main(){
    int n;
    scanf("%d", &n);
    getchar();
    
    char words[n][100];
    for(int i=0; i<n; i++){
        fgets(words[i], 100, stdin);
        words[i][strcspn(words[i], "\n")]='\0';
    }
    
    char dummy[100]="dummy";
    bool found=false;
    for(int i=0; i<n; i++){
        if(strcmp(words[i], dummy) != 0){
        for(int j=i+1; j<n; j++){
            if(areAnagrams(words[i], words[j])){
                found=true;
                printf("%s ", words[i]);
                strcpy(words[j], dummy);
            }
        }
        }
    }
    if(!found){
        printf("No anagrams found\n");
    }
    return 0;
}
"""
5
silent
listen
dog
god
apple

silent dog
"""
```

### Group Anagrams
```
#include<stdio.h>
#include<string.h>
#include<stdbool.h>
#include<ctype.h>
bool areAnagrams(char str1[], char str2[]){
    if(strlen(str1)!=strlen(str2)){
        return false;
    }
    int count1[256]={0};
    int count2[256]={0};
    
    for(int i=0; i<strlen(str1); i++){
        count1[str1[i]]++;
    }
    
    for(int i=0; i<strlen(str2); i++){
        count2[str2[i]]++;
    }
    
    for(int i=0; i<256; i++){
        if(count1[i] != count2[i]){
            return false;
        }
    }
    return true;
}

int main(){
    int n;
    scanf("%d", &n);
    getchar();
    
    char words[n][100];
    for(int i=0; i<n; i++){
        fgets(words[i], 100, stdin);
        words[i][strcspn(words[i], "\n")]='\0';
    }
    
    char dummy[100]="dummy";
    bool found=false;
    for(int i=0; i<n; i++){
        if(strcmp(words[i], dummy) != 0){
        for(int j=i+1; j<n; j++){
            if(areAnagrams(words[i], words[j])){
                found=true;
                printf("%s %s\n", words[i], words[j]);
                strcpy(words[j], dummy);
            }
        }
        }
    }
    if(!found){
        printf("No anagrams found\n");
    }
    return 0;
}
"""
6
silent
god
ate
dog
listen
eat

silent listen
god dog
ate eat
"""
```

### prime anagram pairs from a range
```
#include<stdio.h>
#include<stdbool.h>
#include<ctype.h>
bool prime(int num){
    if(num<=1) {
        return false;
    }
    for(int i=2; i*i<=num; i++){
        if(num%i==0){
            return false;
        }
    }
    return true;
}
void countDigits(int num, int count[]){
    while(num!=0){
        count[num%10]++;
        num/=10;
    }
}
bool areAnagrams(int num1, int num2){
    int count1[10]={0};
    int count2[10]={0};
    countDigits(num1, count1);
    countDigits(num2, count2);
    for(int i=0; i<10; i++){
        if(count1[i] != count2[i]){
            return false;
        }
    }
    return true;
}
void findPrimeAnagramPairs(int start, int end){
    int primes[100];
    int index=0;
    for(int i=start; i<=end; i++){
        if(prime(i)){
            primes[index++]=i;
        }
    }
    printf("Anagram Pairs: \n");
    int found=0;
    for(int i=0; i<index; i++){
        for(int j=i+1; j<index; j++){
        if(areAnagrams(primes[i], primes[j])){
            found=1;
            printf("%d %d\n", primes[i], primes[j]);
        }
    }
    }
    if(!found){
        printf("No Anagram pairs found\n");
    }
}
int main(){
    int start;
    int end;
    scanf("%d", &start);
    scanf("%d", &end);
    findPrimeAnagramPairs(start, end);
    return 0;
}
"""
1
100
Anagram Pairs: 
13 31
17 71
37 73
79 97
"""
```

### Find resultant array after removing anagrams
```
#include<stdio.h>
#include<string.h>
#include<stdbool.h>
#include<ctype.h>
bool areAnagrams(char str1[], char str2[]){
    if(strlen(str1)!=strlen(str2)){
        return false;
    }
    int count1[256]={0};
    int count2[256]={0};
    
    for(int i=0; i<strlen(str1); i++){
        count1[str1[i]]++;
    }
    
    for(int i=0; i<strlen(str2); i++){
        count2[str2[i]]++;
    }
    
    for(int i=0; i<256; i++){
        if(count1[i] != count2[i]){
            return false;
        }
    }
    return true;
}

int main(){
    int n;
    scanf("%d", &n);
    getchar();
    
    char words[n][100];
    for(int i=0; i<n; i++){
        fgets(words[i], 100, stdin);
        words[i][strcspn(words[i], "\n")]='\0';
    }
    char dummy[100]="dummy";
    bool found=false;
    for(int i=0; i<n; i++){
        if(strcmp(words[i], dummy) != 0){
        for(int j=i+1; j<n; j++){
            if(areAnagrams(words[i], words[j])){
                found=true;
                strcpy(words[i], dummy);
                strcpy(words[j], dummy);
            }
        }
        }
    }
    if(!found){
        printf("No anagrams found\n");
    }
    for(int i=0; i<n; i++){
        if(strcmp(words[i], dummy) != 0){
            printf("%s ", words[i]);
        }
    }
    return 0;
}

"""
8
silent
hi
listen
how
padma
dog
god
you
hi how padma you
"""
```

### permutation of a string
```
#include<stdio.h>
#include<string.h>
void swap(char *a, char *b){
    char temp=*a;
    *a=*b;
    *b=temp;
}
void generatePermutation(char *str, int i, int l){
    if(i==l-1){
        printf("%s\n", str);
        return;
    }
    for(int j=i; j<l; j++){
        swap(&str[i], &str[j]);
        
        generatePermutation(str, i+1, l);
        
        swap(&str[i], &str[j]);
    }
}
int main(){
    char str[256];
    fgets(str, 256, stdin);
    str[strcspn(str, "\n")]='\0';
    int l=strlen(str);
    generatePermutation(str, 0, l);
    return 0;
}
"""
ABC

ABC
ACB
BAC
BCA
CAB
CBA
"""
```

### print the pivot index of the given array
```
#include<stdio.h>
#include<ctype.h>

int leftArray(int nums[], int start, int end){
    int sum=0;
    for(int i=start; i<end; i++){
        sum+=nums[i];
    }
    return sum;
}
int rightArray(int nums[], int start, int end){
    int sum=0; 
    for(int i=start; i<end; i++){
        sum+=nums[i];
    }
    return sum;
}
void findPivotIndex(int nums[], int l){
    int leftSum=0;
    int rightSum=0;
    int found=0;
    for(int i=0; i<l; i++){
        leftSum = leftArray(nums, 0, i);
        rightSum = rightArray(nums, i+1, l);
        if(leftSum == rightSum){
            found=1;
            printf("pivot index is: %d", i);
            break;
        }
    }
    if(!found){
        printf("%d", -1);
    }
}
int main(){
    int nums[]={1,7,3,6,5,6};
    int l=sizeof(nums)/sizeof(nums[0]);
    findPivotIndex(nums, l);
    return 0;
}
"""
pivot index is 3
"""
```

### Fibonacci encoding
``` 
#include<stdio.h>
void fibonacciEncoding(int n){
    int prev=1;
    int curr=1;
    int next=prev+curr;
    int arr[100];
    int index=1;
    arr[0]=prev;
    while(next<n){
        arr[index++]=next;
        prev=curr;
        curr=next;
        next=prev+curr;
    }
    int sum=0;
    int result[100];
    int k=0;
    for(int i=index-1; i>=0; i--){
        if(sum+arr[i] <= n){
            sum += arr[i];
            result[k++]=1;
        }
        else{
            result[k++]=0;
        }
    }
    int reversed[k+1];
    int l=0;
    for(int i=k-1; i>=0; i--){
        reversed[l++]=result[i];
    }
    reversed[l++]=1;
    for(int i=0; i<l; i++){
        printf("%d", reversed[i]);
    }
}
int main(){
    int n;
    scanf("%d", &n);
    fibonacciEncoding(n);
}
"""
14
1000011
"""
```

### find whether the given num is Keith Number or not?
```
#include<stdio.h>
int sum(int arr[], int len, int n){
    int total=0;
    for(int i=n-len; i<n; i++){
        total+=arr[i];
    }
    return total;
}
void check(int n){
    int org=n;
    int arr[100];
    int l=0;
    while(org!=0){
        int rem=org%10;
        arr[l++]=rem;
        
        org/=10;
    }
   int reversed[100];
   int index=0;
    for(int i=l-1; i>=0; i--){
        reversed[index++]=arr[i];
    }
    int total=0;
    int found=0;
    while(total <= n){
        if(total == n){
            found=1;
            break;
        }
        total=sum(reversed,l, index);
        reversed[index++]=total;
    }
     if(found){
        printf("Yes\n");
    }
    else{
        printf("No\n");
    }

}
void main(){
    int n;
    scanf("%d", &n);
    check(n);
}
"""
14
yes

15
no

197
yes

1104
yes

31331
yes
"""
```


### print longest substring without repeating characters
```
#include<stdio.h>
#include<string.h>
#include<stdbool.h>
#include<ctype.h>
bool check(char arr[], int n){
    if(n==1)
    return true;
    for(int i=0; i<n; i++){
        for(int j=i+1; j<n; j++){
            if(arr[i] == arr[j]){
                return false;
            }
        }
    }
    return true;
}
int main(){
    char str[256];
    fgets(str, 256, stdin);
    str[strcspn(str, "\n")]='\0';
    int l=strlen(str);
    char arr[256];
    int longLen=0;
    int currLen=0;
    int startIndex=0;
    for(int i=0; i<l; i++){
        for(int j=i+1; j<l; j++){
            int index=0;
           for(int k=i; k<=j; k++){
                arr[index]=str[k];
                index++;
           }
            if(!check(arr, index)){
                break;
            }
            currLen=j-i+1;
            if(currLen > longLen){
                longLen = currLen;
                startIndex=i;
            }
    }
        }
    printf("%d\n", longLen);
    for(int i=startIndex; i<startIndex+longLen; i++){
        printf("%c", str[i]);
    }
    return 0;
}
"""
padmavathiama
5 //longestSubstring length
vathi //longest substring
"""
```

### print circular prime numbers between a given range:
```
#include<stdio.h>
#include<math.h>
#include<stdbool.h>
bool isPrime(int n){
    if(n<=1){
        return false;
    }
    for(int i=2; i*i<=n; i++){
        if(n%i==0){
            return false;
        }
    }
    return true;
}
int numOfDigits(int n){
    int l=0;
    while(n!=0){
        int rem=n%10;
        l++;
        n/=10;
    }
    return l;
}
int rotateNum(int n, int l){
    int rem=n%10;
    int quo=n/10;
    int shift=pow(10, l-1);
    
    return rem*shift+quo;
}
bool circularPrime(int currNum, int org, int l){
    if(currNum == org){
        return true;
    }
    if(!isPrime(currNum)){
        return false;
    }
    int rotated=rotateNum(currNum, l);
    
    return circularPrime(rotated, org, l);
    
}
bool isCirPrime(int n){
   if(!isPrime(n)){
        return false;
    }
    int l=numOfDigits(n);
    int rotated=rotateNum(n, l);
    circularPrime(rotated, n, l);
    
}
void check(int start, int end){
    for(int i=start; i<=end; i++){
        if(isCirPrime(i)){
            printf("%d ", i);
        }
    }
}
int main(){
    int start;
    scanf("%d", &start);
    int end;
    scanf("%d", &end);
   check(start, end);
return 0;
}
"""
1 //start
200 //end
2 3 5 7 11 13 17 31 37 71 73 79 97 113 131 197 199
"""
```

### decode string (Leetcode_394)
```
#include<stdio.h>
#include<string.h>
#include<ctype.h>
void decode(char str[], int l){
    int nums[100];
    int numsIndecies[100];
    int m=0;
    int n=0;
    for(int i=0; i<l; i++){
        if(str[i] >= '1' && str[i] <= '9'){
            int num=str[i]-'0';
            nums[m++]=num;
            numsIndecies[n++]=i;
        }
    }
    for(int i=0; i<m-1; i++){
        char word[100];
        int index=0;
        for(int j=numsIndecies[i]+1; j<numsIndecies[i+1]; j++){
            if(str[j] >= 'a' && str[j] <= 'z'){
            word[index++]=str[j];
            }
        }
        for(int k=0; k<nums[i]; k++){
        printf("%s", word);
        }
    }
    for(int i=m-1; i<m; i++){
        char word[100];
        int index=0;
        for(int j=numsIndecies[i]+1; j<l; j++){
            if(str[j] >= 'a' && str[j] <= 'z'){
                word[index++]=str[j];
            }
        }
        for(int k=0; k<nums[i]; k++){
        printf("%s", word);
        }
    }
}
void main(){
    char str[256];
    fgets(str, 256, stdin);
    str[strcspn(str, "\n")]='\0';
    int l=strlen(str);
    decode(str, l);
}
"""
2[ab]3[bc]4[cd]2[jk]
ababbcbcbccdcdcdcdjkjk
"""
```

### convert binary to integer
```
#include<stdio.h>
#include<string.h>
#include<ctype.h>
void convert(long binary){
    char str[256];
    snprintf(str, sizeof(str), "%ld", binary);
    int num=0;
    int arr[]={128,64,32,16,8,4,2,1};
    int len=7;
    for(int i=0; i<strlen(str); i++){
        if(str[i]=='1'){
            num+=arr[len-i];
        }
    }
    printf("%d", num);
}
void main(){
    long binary;
    scanf("%ld", &binary);
    convert(binary);
}
"""
1101
13
"""
```

### string match
```
#include<stdio.h>
#include<string.h>
#include<ctype.h>
#include<stdlib.h>
char* reverse(char *str, int n){
    char* temp=(char *) malloc ((n+1) * sizeof(char));
    int index=0;
    for(int i=n-1; i>=0; i--){
        temp[index++]=str[i];
    }
    temp[index]='\0';
    return temp;
}
void check(char words[][100], int n){
    char reversed[n][100];
    char *temp;
    for(int i=0; i<n; i++){
        int len=strlen(words[i]);
        temp=reverse(words[i], len);
        strcpy(reversed[i], temp);
        free(temp);
    }
    char *temp2;
    for(int i=0; i<n; i++){
        for(int j=i+1; j<n; j++){
            if(strcmp(reversed[i], reversed[j]) > 0){
                strcpy(temp2, reversed[i]);
                strcpy(reversed[i], reversed[j]);
                strcpy(reversed[j], temp2);
            }
        }
    }
    char descending[n][100];
    int index=0;
    for(int i=n-1; i>=0; i--){
        strcpy(descending[index++], reversed[i]);
    }
    
    for(int i=0; i<n; i++){
        printf("%s - %s ", reversed[i], descending[i]);
    }
}
int main(){
    int n;
    scanf("%d", &n);
    getchar();
    char words[n][100];
    for(int i=0; i<n; i++){
        fgets(words[i], 100, stdin);
        words[i][strcspn(words[i], "\n")]='\0';
    }
    check(words, n);
    return 0;
}
"""
4
functions
program
Program
and
dna - snoitcnuf margorP - margorp margorp - margorP snoitcnuf - dna
"""
```

### **reverse word --> remove duplicates --> count vowels**
```
#include<stdio.h>
#include<string.h>
#include<ctype.h>
#include<stdlib.h>
char* reverse(char *str){
    int l=strlen(str);
    char *temp=(char *) malloc((l+1) * sizeof(char));
    int m=0;
    for(int i=l-1; i>=0; i--){
        temp[m++]=str[i];
    }
    temp[m]='\0';
    return temp;
    free(temp);
}
int countVowels(char *str){
    int l=strlen(str);
    int count=0;
    for(int i=0; i<l; i++){
        char c=tolower(str[i]);
        if(str[i]=='a' || str[i]=='e' || str[i]=='i' || str[i]=='o' || str[i]=='u'){
            count++;
        }
    }
    return count;
}
char* removeDup(char *str){
    char *temp;
    int m=0;
    int l=strlen(str);
    for(int i=0; i<l; i++){
        if(str[i]!='\0'){
        for(int j=i+1; j<l; j++){
           if(str[i]==str[j]){
               str[j]='\0';
           } 
        }
    }
    }
    for(int i=0; i<l; i++){
        if(str[i]!='\0'){
        temp[m++]=str[i];
    }
    }
    return temp;
}
int main(){
    char str[256];
    fgets(str, 256, stdin);
    str[strcspn(str, "\n")]='\0';
    
    char *temp=reverse(str);
    char *current=removeDup(temp);
    int count=countVowels(current);
    printf("%d", count);
    
}
"""
padmavathi
2
"""
```

### Palindrome Detection and Sorting 
### reverse words --> find palindromes --> sort palindromes in ascending --> print words
```
#include<stdio.h>
#include<string.h>
#include<stdbool.h>
#include<stdlib.h>
#include<ctype.h>
char* reverse(char *str, int n){
    char* temp=(char *) malloc ((n+1) * sizeof(char));
    int index=0;
    for(int i=n-1; i>=0; i--){
        temp[index++]=str[i];
    }
    temp[index]='\0';
    return temp;
    free(temp);
}
bool isPalindrome(char str[]){
    int l=strlen(str);
    int left=0;
    int right=l-1;
    while(left < right){
        if(str[left]!=str[right]){
            return false;
        }
        left++;
        right--;
    }
    return true;
}
void check(char words[][100], int n){
    char reversed[n][100];
    char *temp;
    for(int i=0; i<n; i++){
        int len=strlen(words[i]);
        temp = reverse(words[i], len);
        strcpy(reversed[i], temp);
    }
    char palindromes[100][100];
    int m=0;
    for(int i=0; i<n; i++){
        if(isPalindrome(reversed[i])){
            strcpy(palindromes[m++], reversed[i]);
        }
    }
    char temp2[100];
    for(int i=0; i<m; i++){
        for(int j=i+1; j<m; j++){
            if(strcmp(palindromes[i], palindromes[j]) < 0){
                strcpy(temp2, palindromes[i]);
                strcpy(palindromes[i], palindromes[j]);
                strcpy(palindromes[j], temp2);
            }
        }
    }
    for(int i=0; i<m; i++){
        printf("%s ", palindromes[i]);
    }
}
int main(){
    int n;
    scanf("%d", &n);
    getchar();
    char words[n][100];
    for(int i=0; i<n; i++){
        fgets(words[i], 100, stdin);
        words[i][strcspn(words[i], "\n")]='\0';
    }
    check(words, n);
}
"""
5
racecar
madam
are
hi
asa
racecar madam asa
"""
```

### Anagram Grouping 
**reverse words --> print anagram pairs from reversed words**
```
#include<stdio.h>
#include<string.h>
#include<ctype.h>
#include<stdlib.h>
#include<stdbool.h>
bool areAnagrams(char str1[], char str2[]){
    int l1=strlen(str1);
    int l2=strlen(str2);
    if(l1!=l2){
        return false;
    }
    
    int count1[256]={0};
    int count2[256]={0};
    
    for(int i=0; i<l1; i++){
        count1[str1[i]]++;
    }
    for(int i=0; i<l2; i++){
        count2[str2[i]]++;
    }
    
    for(int i=0; i<256; i++){
        if(count1[i] != count2[i]){
            return false;
        }
    }
    return true;
}
char* reverse(char *str, int n){
    char* temp=(char *) malloc ((n+1) * sizeof(char));
    int index=0;
    for(int i=n-1; i>=0; i--){
        temp[index++]=str[i];
    }
    temp[index]='\0';
    return temp;
    free(temp);
}
void groupAnagrams(char words[][100], int n){
    char reversed[n][100];
    char *temp;
    for(int i=0; i<n; i++){
        int len=strlen(words[i]);
        temp=reverse(words[i], len);
        strcpy(reversed[i], temp);
    }
    for(int i=0; i<n; i++){
        for(int j=i+1; j<n; j++){
            if(areAnagrams(reversed[i], reversed[j])){
                printf("%s %s\n", reversed[i], reversed[j]);
            }
        }
    }
}
int main(){
    int n;
    scanf("%d", &n);
    getchar();
    char words[n][100];
    for(int i=0; i<n; i++){
        fgets(words[i], 100, stdin);
        words[i][strcspn(words[i], "\n")]='\0';
    }
    groupAnagrams(words, n);
}
"""
5
silet n
lisen
am
god
dog
nelis nesil
dog god
"""
```

### Remove Duplicates After Reversal
**reverse words --> remove duplicates --> sort in ascending lexicographical order --> print those words**
```
#include<stdio.h>
#include<string.h>
#include<ctype.h>
#include<stdlib.h>
char * reverse(char *str, int n){
    char *temp=(char *) malloc ((100) * sizeof(char));
    int m=0;
    for(int i=n-1; i>=0; i--){
        temp[m++]=str[i];
    }
    temp[m]='\0';
    return temp;
    free(temp);
}
char * removeDuplicates(char *str, int n){
    char *temp=(char*) malloc ((100+1) *sizeof(char));
    int m=0;
    for(int i=0; i<n; i++){
        if(str[i]!='\0'){
        for(int j=i+1; j<n; j++){
            if(str[i]==str[j]){
                str[j]='\0';
            }
            }
        }
        }
        for(int i=0; i<n; i++){
            if(str[i]!='\0'){
                temp[m++]=str[i];
            }
        }
    temp[m]='\0';
    return temp;
    free(temp);
}
void removeDup(char words[][100], int n){
    char reversed[n][100];
    char *temp;
    for(int i=0; i<n; i++){
        int len=strlen(words[i]);
        temp=reverse(words[i], len);
        strcpy(reversed[i], temp);
    }
    char *temp2;
    char removed[n][100];
    for(int i=0; i<n; i++){
        int len=strlen(reversed[i]);
        temp2=removeDuplicates(reversed[i], len);
        strcpy(removed[i], temp2);
    }
    char * temp3;
    for(int i=0; i<n; i++){
       for(int j=i+1; j<n; j++){
           if(strcmp(removed[i], removed[j]) > 0){
               strcpy(temp3, removed[i]);
               strcpy(removed[i], removed[j]);
               strcpy(removed[j], temp3);
           }
       }
    }
    for(int i=0; i<n; i++){
        printf("%s ", removed[i]);
    }
}
int main(){
    int n;
    scanf("%d", &n);
    getchar();
    char words[n][100];
    for(int i=0; i<n; i++){
        fgets(words[i], 100, stdin);
        words[i][strcspn(words[i], "\n")]='\0';
    }
    removeDup(words, n);
}
"""
4
padma
akila
jaga
kavi
agj alik amdp ivak 
"""
```

### Longest and Shortest Word After Reversal
**reverse words --> find longest and smallest based on their length and print those along with their lengths**
```
#include<stdio.h>
#include<string.h>
#include<stdbool.h>
#include<stdlib.h>
#include<ctype.h>
char * reverse(char *str, int n){
    char *temp=(char *) malloc ((100) * sizeof(char));
    int l=0;
    for(int i=n-1; i>=0; i--){
        temp[l++]=str[i];
    }
    temp[l]='\0';
    return temp;
    free(temp);
}
void *findLong(char words[][100], int n){
    char *longest;
    strcpy(longest, words[0]);
    for(int i=1; i<n; i++){
        if(strlen(longest) < strlen(words[i])){
            strcpy(longest, words[i]);
        }
    }
    return longest;
}
char * findSmall(char words[][100], int n){
    char *smallest;
    strcpy(smallest, words[0]);
    for(int i=1; i<n; i++){
        if(strlen(smallest) > strlen(words[i])){
            strcpy(smallest, words[i]);
        }
    }
    return smallest;
}
void findWords(char words[][100], int n){
    char reversed[n][100];
    char *temp;
    for(int i=0; i<n; i++){
        int len=strlen(words[i]);
        temp=reverse(words[i], len);
        strcpy(reversed[i], temp);
    }
    
    char *longest= findLong(reversed, n);
    printf("%s %d\n", longest, strlen(longest));
    char *smallest = findSmall(reversed, n);
    printf("%s %d", smallest, strlen(smallest));
}
int main(){
    int n;
    scanf("%d", &n);
    getchar();
    char words[n][100];
    for(int i=0; i<n; i++){
        fgets(words[i], 100, stdin);
        words[i][strcspn(words[i], "\n")]='\0';
    }
    findWords(words, n);
}
"""
4
akila
padmavathi
h jaga
kavi
ihtavamdap 10
agaj 4
"""
```

### Words Starting with Vowels
**reverse words --> seperate as vowel and non vowel words based on first character**
```
#include<stdio.h>
#include<string.h>
#include<stdlib.h>
#include<ctype.h>
#include<stdbool.h>
char *reverse(char *str, int n){
    char *temp=(char *) malloc ((100) * sizeof(char));
    int index=0;
    for(int i=n-1; i>=0; i--){
        temp[index++]=str[i];
    }
    temp[index]='\0';
    return temp;
    free(temp);
}
bool hasVowel(char *str){
    int l=strlen(str);
    char c=tolower(str[0]);
    if(c == 'a' || c == 'e' || c == 'i' || c == 'o' || c == 'u'){
        return true;
    }
    return false;
}
void findWords(char words[][100], int n){
    char reversed[n][100];
    char *temp;
    for(int i=0; i<n; i++){
        int len=strlen(words[i]);
        temp=reverse(words[i], len);
        strcpy(reversed[i], temp);
    }
    char vowelWords[n][100];
    int l=0;
    char nonVowelWords[n][100];
    int m=0;
    for(int i=0; i<n; i++){
        if(hasVowel(reversed[i])){
            strcpy(vowelWords[l++], reversed[i]);
        }
        else{
            strcpy(nonVowelWords[m++], reversed[i]);
        }
    }
    for(int i=0; i<l; i++){
        printf("%s ", vowelWords[i]);
    }
    printf("\n");
     for(int i=0; i<m; i++){
        printf("%s ", nonVowelWords[i]);
    }
}
int main(){
    int n;
    scanf("%d", &n);
    getchar();
    char words[n][100];
    for(int i=0; i<n; i++){
        fgets(words[i], 100, stdin);
        words[i][strcspn(words[i], "\n")]='\0';
    }
    findWords(words, n);
}
"""
5
hi
how
are
you
pa
ih era uoy ap //vowel words
woh //non vowel words
"""
```
