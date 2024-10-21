## Recursion:
* A function is calling itself directly or indirectly called as "Recursion".

### Leetcode_5 - 5. Longest Palindromic Substring:
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


### Sum of odd numbers using recursion
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
