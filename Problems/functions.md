## Recursion:
* A function is calling itself directly or indirectly called as "Recursion".

### 1. Leetcode_5 - 5. Longest Palindromic Substring:
- using c
```
bool isPalindrome(char str[], int start, int end){
    while(start < end){
        if(str[start] != str[end]){
            return false;
        }
        start++;
        end--;
    }
    return true;
}
char* longestPalindrome(char* s) {
    int start=0;
        int maxLength=1;
        int len=strlen(s);
        for(int i=0; i<len; i++){
            for(int j=i+1; j<len; j++){
                if(isPalindrome(s, i, j)){
                    if(j-i+1 > maxLength){
                        maxLength=j-i+1;
                        start=i;
                    }
                }
            }
        }
        static char res[100];
        int index=0;
        for(int k=start; k < start + maxLength; k++){
            res[index++]=s[k];
        }
        res[index]='\0';
        return res;
}
"""
babad //input
bab // output
"""
```


### 2. Sum of odd numbers using recursion
```
#include<stdio.h>
int sumOfOdd(int n){
    if(n<=0){
        return 0;
    }
    else if(n%2!=0){
        return n + sumOfOdd(n-2);
    }
    else{
        return sumOfOdd(n-1);
    }
    
}
int main(){
    int n;
    scanf("%d", &n);
    int res=sumOfOdd(n);
    printf("%d", res);
    return 0;
}
"""
10 //n
25 //sum of odd
"""
```

### 3. Sum of even number using recursion
```
#include<stdio.h>
int sumOfEven(int n){
    if(n<=0){
        return 0;
    }
    else if(n%2==0){
        return n + sumOfEven(n-2);
    }
    else{
        return sumOfEven(n-1);
    }
    
}
int main(){
    int n;
    scanf("%d", &n);
    int res=sumOfEven(n);
    printf("%d", res);
    return 0;
}
"""
10 //n
30 //sum of even
"""
```

### 4. factorial of a number
```
#include<stdio.h>
int factOfNum(int n){
    if(n==0 || n==1){
        return 1;
    }
    else{
        return n * factOfNum(n-1);
    }
}
int main(){
    int n;
    scanf("%d", &n);
    int res=factOfNum(n);
    printf("%d", res);
    return 0;
}
"""
5 //5!
120
"""
```

### 5. Fibonacci Series using Recursion
```
#include<stdio.h>
int fibonacci(int n){
    if(n==0){
        return 0;
    }
    else if(n==1){
        return 1;
    }
    else{
        return fibonacci(n-1) + fibonacci(n-2);
    }
}
int main(){
    int n;
    scanf("%d", &n);
    int res=fibonacci(n);
    printf("%d", res);
    return 0;
}
"""
6 //n
8 //fib of 6 is 8
"""
```

### 6. Sum of digits using Recursion
```
#include<stdio.h>
int sumOfDigits(int n){
    if(n==0){
        return 0;
    }
    else{
        return (n%10) + sumOfDigits(n/10);
    }
}
int main(){
    int n;
    scanf("%d", &n);
    int res=sumOfDigits(n);
    printf("%d", res);
    return 0;
}
"""
123 //n
6 //sum of 123
"""
```

### 7. Check if the num is circular Prime or not
```
#include<stdio.h>
#include<stdbool.h>
#include<math.h>
bool isPrime(int num){
    if(num<=1){
        return false;
    }
    for(int i=2; i<num; i++){
        if(num%i==0){
            return false;
        }
    }
    return true;
}
int numOfDigits(int num){
    int n=0;
    while(num!=0){
        int rem=num%10;
        n++;
        num /=10;
    }
    return n;
}
int rotateNum(int num, int digits){
    int rem=num%10;
    int quo=num/10;
    int shift=pow(10, digits-1);
    
    return rem * shift + quo;
}
bool isCircularPrimeHelper(int currNum, int org, int digits){
    if(currNum == org){
        return true;
    }
    if(!isPrime(currNum)){
        return false;
    }
    int rotated = rotateNum(currNum, digits);
    
    return isCircularPrimeHelper(rotated, org, digits);
}
bool isCircularPrime(int num){
    if(!isPrime(num)){
        return false;
    }
    
    int digits = numOfDigits(num);
    int rotated = rotateNum(num, digits);
    
    return isCircularPrimeHelper(rotated, num, digits);
}
int main(){
    int num;
    scanf("%d", &num);
    if(isCircularPrime(num)){
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

123
No
"""
```

### 8. Group Anagrams
```
#include<stdio.h>
#include<stdbool.h>
#include<string.h>
#include<stdlib.h>
bool areAnagrams(char *str1, char *str2){
    int count1[26]={0};
    int count2[26]={0};
    
    if(strlen(str1) != strlen(str2)){
        return false;
    }
    
    for(int i=0; str1[i]!='\0'; i++){
        count1[str1[i]-'a']++;
        count2[str2[i]-'a']++;
    }
    for(int i=0; i<26; i++){
        if(count1[i] != count2[i]){
            return false;
        }
    }
    return true;
}
void groupAnagrams(char* str[], int n){
    int grouped[n];
    memset(grouped, 0, sizeof(grouped));
    
    for(int i=0; i<n; i++){
        if(grouped[i]){
            continue;
        }
        printf("%s ", str[i]);
        
        grouped[i]=1;
        
        for(int j=i+1; j<n; j++){
            if(!grouped[j] && areAnagrams(str[i], str[j])){
                printf("%s", str[j]);
                
                grouped[j]=1;
            }
        }
        printf("\n");
    }
}
int main(){
    int n;
    scanf("%d", &n);
    char* str[n];
    for(int i=0; i<n; i++){
        str[i]=(char *)malloc(100 * sizeof(char));
        scanf("%s", str[i]);
    }
    groupAnagrams(str, n);
    for(int i=0; i<n; i++){
        free(str[i]);
    }
    return 0;
}
"""
5 //n - number of words
silent
ate
listen
eat
apple

silent listen
ate eat
apple
"""
```

### 9. Find the first occurance of each anagram
```
#include<stdio.h>
#include<string.h>
#include<stdbool.h>
#include<math.h>
#include<stdlib.h>
int areAnagrams(char *str1, char *str2){
    if(strlen(str1) != strlen(str2)){
        return 0;
    }
    int count1[26]={0};
    int count2[26]={0};
    
    for(int i=0; str1[i]!='\0'; i++){
        count1[str1[i] - 'a']++;
        count2[str2[i] - 'a']++;
    }
    for(int i=0; i<26; i++){
        if(count1[i] != count2[i]){
            return 0;
        }
    }
    return 1;
}
void firstOccurAnagram(int i, char *str[], int n){
    if(i>=n){
        return;
    }
    printf("%s\n", str[i]);
    
    for(int j=i+1; j<n; j++){
        if(areAnagrams(str[i], str[j])){
            for(int k=j; k<n-1; k++){
                strcpy(str[k], str[k+1]);
            }
            n--;
            j--;
        }
    }
    firstOccurAnagram(i+1, str, n);
}
void main(){
    int n;
    scanf("%d", &n);
    char *str[n];
    for(int i=0; i<n; i++){
        str[i]=(char *)malloc(100 * sizeof(char));
        scanf("%s", str[i]);
    }
    firstOccurAnagram(0, str, n);
    for(int i=0; i<n; i++){
        free(str[i]);
    }
    
}
"""
5
listen
silent
man
eat
ate

"""
listen
man
eat
"""
```



## PS LIST:

### 1. Circular Prime:
```
#include<stdio.h>
#include<stdbool.h>
#include<math.h>
bool isPrime(int num){
    if(num<2){
        return false;
    }
    for(int i=2; i<=num/2; i++){
        if(num%i==0){
            return false;
        }
    }
    return true;
}
int rotateNum(int num, int len){
    int rem=num % 10;
    num /= 10;
    return rem * pow(10, len-1) + num;
}
bool isCircularPrime(int num){
    int len=0;
    int temp=num;
    while(temp > 0){
        len++;
        temp /= 10;
    }
    int rotated=num;
    for(int i=0; i<len; i++){
        if(!isPrime(rotated)){
            return false;
        }
        rotated=rotateNum(rotated, len);
    }
    return true;
}
int main(){
    int num;
    scanf("%d", &num);
    if(isCircularPrime(num)){
        printf("Yes\n");
    }
    else{
        printf("No\n");
    }
    return 0;
}
"""
971
Yes
"""
```

### 2. Find the prime anagram pairs in the given range
```
#include<stdio.h>
#include<stdbool.h>
bool isPrime(int num){
    if(num < 2){
        return false;
    }
    for(int i=2; i<=num/2; i++){
        if(num%i==0){
            return false;
        }
    }
    return true;
}
void countdigits(int num, int digitCount[]){
    while(num > 0){
        digitCount[num % 10]++;
        num /= 10;
    }
}
bool areAnagrams(int num1, int num2){
    int count1[10]={0};
    int count2[10]={0};
    countdigits(num1, count1);
    countdigits(num2, count2);
    
    for(int i=0; i<10; i++){
        if(count1[i] != count2[i]){
            return false;
        }
    }
    return true;
    
}
int findAnagramPairs(int start, int end){
    int primes[100];
    int index=0;
    for(int i=start; i<=end; i++){
        if(isPrime(i)){
            primes[index++]=i;
        }
    }
    printf("Anagram pairs:\n");
    for(int i=0; i<index; i++){
        for(int j=i+1; j<index; j++){
            if(areAnagrams(primes[i], primes[j])){
                printf("%d %d\n", primes[i], primes[j]);
            }
        }
    }
    
}
int main(){
    int start;
    scanf("%d", &start);
    int end;
    scanf("%d", &end);
    findAnagramPairs(start, end);
    return 0;
    
}
"""
1 //start
100 //end
Anagram pairs:
13 31
17 71
37 73
79 97
"""
```

### 3. Sum of even numbers in an array using recursion
```
#include<stdio.h>
int sumOfOdd(int arr[], int n){
    if(n==0){
        return 0;
    }
    int lastElement=arr[n-1];
    if(lastElement % 2 == 0){
        return lastElement+sumOfOdd(arr, n-1);
    }
    else{
        return sumOfOdd(arr, n-1);
    }
    
}
int main(){
    int n;
    scanf("%d", &n);
    int arr[n];
    for(int i=0; i<n; i++){
        scanf("%d", &arr[i]);
    }
    int sum = sumOfOdd(arr, n);
    printf("%d", sum);
    return 0;
}
"""
6
1 2 3 4 5 6
12
"""
```

### 4.Sum of odd numbers in an array using recursion
```
#include<stdio.h>
int sumOfOdd(int arr[], int n){
    if(n==0){
        return 0;
    }
    int lastElement=arr[n-1];
    if(lastElement % 2 == 0){
        return lastElement+sumOfOdd(arr, n-1);
    }
    else{
        return sumOfOdd(arr, n-1);
    }
    
}
int main(){
    int n;
    scanf("%d", &n);
    int arr[n];
    for(int i=0; i<n; i++){
        scanf("%d", &arr[i]);
    }
    int sum = sumOfOdd(arr, n);
    printf("%d", sum);
    return 0;
}
"""
6
1 2 3 4 5 6
9
"""
```

### 5. replace vowels with its next vowel and consonants with next consonant in a sentence
```
#include<stdio.h>
#include<string.h>
#include<ctype.h>
#include<stdbool.h>
char nextVowel(char ch){
    switch(tolower(ch)) {
        case 'a':
        return (ch == 'a') ? 'e' : 'E';
        case 'e':
        return (ch == 'e') ? 'i' : 'I';
        case 'i':
        return (ch == 'i') ? 'o' : 'O';
        case 'o':
        return (ch == 'o') ? 'u' : 'U';
        case 'u':
        return (ch == 'u') ? 'a' : 'A';
        default:
            return ch;
    }
}

bool isAlpha(char ch){
    return (ch >= 'a' && ch<='z') || (ch>='A' && ch<='Z');
}

void replaceChar(char word[]){
    int len=strlen(word);
    for(int i=0; i<len; i++){
        char ch=word[i];
        if(isAlpha(ch)){
        if(ch == 'a' || ch=='e' || ch=='i' || ch=='o' || ch=='u'
           || ch =='A' || ch=='E' || ch=='I' || ch=='O' || ch=='U'){
            word[i]=nextVowel(ch);
        }
        else{
            word[i]=ch+1;
        }
        }
    }
}
int main() {
    char word[256];
    fgets(word, 256, stdin);
    word[strcspn(word, "\n")] = '\0';
    replaceChar(word);
    printf("%s", word);
    return 0;
}
"""
Hello World
Iimmu Xusme
"""
```
