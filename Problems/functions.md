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
