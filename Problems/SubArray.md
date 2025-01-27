## Sub Array problems

### 1. Maximum Subarray Sum (Kadane's Algorithm)
* Problem: Find the contiguous subarray within an array that has the largest sum.
* Example:
* Input: [-2, 1, -3, 4, -1, 2, 1, -5, 4]
* Output: 6 (Subarray: [4, -1, 2, 1])
```
#include<stdio.h>
int sum(int arr[], int s, int e){
    int sum=0;
    for(int i=s; i<=e; i++){
        sum+=arr[i];
    }
    return sum;
}
void find(int arr[], int n){
    int maxSum=0; int startIndex=0, endIndex=0; int len=0;
    for(int i=0; i<n; i++){
        for(int j=i+1; j<n; j++){
            int currSum=sum(arr, i, j);
            len=j-i+1;
            if(currSum > maxSum){
                maxSum=currSum;
                startIndex=i;
                endIndex=j;
            }
        }
    }
    int res[100]; int l=0;
    for(int i=startIndex; i<=endIndex; i++){
        res[l++]=arr[i];
    }
    printf("%d\n", maxSum);
    for(int i=0; i<l; i++){
        printf("%d ", res[i]);
    }
}
int main(){
    int n;
    scanf("%d", &n);
    int arr[n];
    for(int i=0; i<n; i++){
        scanf("%d", &arr[i]);
    }
    find(arr, n);
}
"""
9
-2 1 -3 4 -1 2 1 -5 4
6
4 -1 2 1 
"""
```

### Subarray with a Given Sum
* Problem: Find a subarray with a given sum (non-negative integers).
* Example:
* Input: arr = [1, 2, 3, 7, 5], target = 12
* Output: [2, 4] (Subarray: [2, 3, 7])
```
#include<stdio.h>
#include<stdbool.h>
int Sum(int arr[], int s, int e){
    int sum=0;
    for(int i=s; i<=e; i++){
        sum+=arr[i];
    }
    return sum;
}
void find(int arr[], int n, int t){
    int si=0, ei=0;
    bool found=false;
    for(int i=1; i<=n; i++){
        if(!found){
        for(int j=i+1; j<=n; j++){
          // check(arr, i, j);
           int sum=Sum(arr, i, j);
           if(sum == t){
               found=true;
               si=i; ei=j;
               break;
           }
           }
    }
    }
    printf("%d %d", si, ei);
    
}
int main(){
    int n;
    scanf("%d", &n);
    int arr[n+1];
    for(int i=1; i<=n; i++){
        scanf("%d", &arr[i]);
    }
    int target;
    scanf("%d", &target);
    find(arr, n, target);
}
"""
5
1 2 3 7 5
12
2 4
"""
```
  
### Longest Sub array with equal zeros and ones
```
#include<stdio.h>
#include<stdbool.h>
bool check(int arr[], int s, int e){
    int zeros_count=0, ones_count=0;
    for(int i=s; i<=e; i++){
        if(arr[i] == 0){
            zeros_count++;
        }
        else{
            ones_count++;
        }
    }
    if(zeros_count == ones_count){
        return true;
    }
    return false;
}
void find(int arr[], int n){
    int maxLen=0,si=0, ei=0;
    for(int i=0; i<n; i++){
        for(int j=i+1; j<n; j++){
            if(check(arr, i, j)){
                int currLen=j-i+1;
                if(currLen > maxLen){
                    maxLen=currLen;
                    si=i;
                    ei=j;
                }
            }
        }
    }
    printf("%d\n", maxLen);
    for(int i=si; i<=ei; i++){
        printf("%d ", arr[i]);
    }
}
int main(){
    int n;
    scanf("%d", &n);
    int arr[100];
    for(int i=0; i<n; i++){
        scanf("%d", &arr[i]);
    }
    find(arr, n);
}
"""
8
0 1 1 0 1 0 1 1 
6 //maxLen
0 1 1 0 1 0  //subarray with equal zeros and ones
"""
```

### Smallest Subarray with a Sum Greater Than X
* Problem: Find the length of the smallest subarray with a sum greater than a given value X.
* Example:
* Input: arr = [1, 4, 45, 6, 0, 19], X = 51
* Output: 3
```
#include<stdio.h>
#include<stdbool.h>
#include<limits.h>
bool check(int arr[], int s, int e, int x){
    int sum=0;
    for(int i=s; i<=e; i++){
        sum+=arr[i];
    }
    if(sum > x){
        return true;
    }
    else{
        return false;
    }
}
void find(int arr[], int n, int x){
    int minLen=INT_MAX, si=0, ei=0;
    for(int i=0; i<n; i++){
        for(int j=i+1; j<n; j++){
            if(check(arr, i, j, x)){
                int currLen=j-i+1;
                if(currLen < minLen){
                    minLen=currLen;
                    si=i;
                    ei=j;
                }
            }
        }
    }
    printf("%d\n", minLen);
    for(int i=si; i<=ei; i++){
        printf("%d ", arr[i]);
    }
}
int main(){
    int n;
    scanf("%d", &n);
    int arr[100];
    for(int i=0; i<n; i++){
        scanf("%d", &arr[i]);
    }
    int x;
    scanf("%d", &x);
    find(arr, n, x);
}
"""
6
1 4 45 6 0 19
51
3 //minLen
4 45 6 //minlen sub array with sum of greater than x
"""
```

### Maximum Product Subarray
* Problem: Find the contiguous subarray with the maximum product.
* Example:
* Input: [2, 3, -2, 4]
* Output: 6 (Subarray: [2, 3])
```
#include<stdio.h>
#include<limits.h>
int product(int arr[], int s, int e){
    int pro=1;
    for(int i=s; i<=e; i++){
        pro *= arr[i];
    }
    return pro;
}
void find(int arr[], int n){
    int maxProduct=INT_MIN, si=0, ei=0;
    for(int i=0; i<n; i++){
        for(int j=i+1; j<n; j++){
           int currProduct=product(arr, i, j);
            if(currProduct > maxProduct){
                maxProduct=currProduct;
                si=i;
                ei=j;
            }
        }
    }
    printf("%d\n", maxProduct);
    for(int i=si; i<=ei; i++){
        printf("%d ", arr[i]);
    }
    
}
int main(){
    int n;
    scanf("%d", &n);
    int arr[100];
    for(int i=0; i<n; i++){
        scanf("%d", &arr[i]);
    }
    find(arr, n);
}
"""
4
10 20 0 30
200
10 20 
"""
```

### Longest Subarray with Sum Divisible by K
* Problem: Find the length of the longest subarray with a sum divisible by K.
* Example:
* Input: arr = [2, 7, 6, 1, 4, 5], K = 3
* Output: 4
```
#include<stdio.h>
#include<stdbool.h>
#include<limits.h>
bool check(int arr[], int s, int e, int k){
    int sum=0;
    for(int i=s; i<=e; i++){
        sum+=arr[i];
    }
    if(sum%k==0){
        return true;
    }
    else{
        return false;
    }
}
void find(int arr[], int n, int k){
    int maxLen=0, si=0, ei=0;
    for(int i=0; i<n; i++){
        for(int j=i+1; j<n; j++){
           if(check(arr, i, j, k)){
               int currLen=j-i+1;
               if(currLen > maxLen){
                   maxLen=currLen;
                   si=i;
                   ei=j;
               }
           }
        }
    }
    printf("%d\n", maxLen);
    for(int i=si; i<=ei; i++){
        printf("%d ", arr[i]);
    }
    
}
int main(){
    int n;
    scanf("%d", &n);
    int arr[100];
    for(int i=0; i<n; i++){
        scanf("%d", &arr[i]);
    }
    int k;
    scanf("%d", &k);
    find(arr, n, k);
}
"""
6
2 7 6 1 4 5
3
4
7 6 1 4
"""
```

### Find Subarrays with Exactly K Distinct Elements
* Problem: Count the subarrays that have exactly K distinct elements.
* Example:
* Input: arr = [1, 2, 1, 3, 4], K = 2
* Output: 7

```
#include<stdio.h>
void find(int arr[], int n, int k){
    int count=0;
    for(int i=0; i<n; i++){
        for(int j=i+1; j<n; j++){
           if(j-i+1 == k){
               count++;
           }
        }
    }
   printf("%d", count);
}
int main(){
    int n;
    scanf("%d", &n);
    int arr[100];
    for(int i=0; i<n; i++){
        scanf("%d", &arr[i]);
    }
    int k;
    scanf("%d", &k);
    find(arr, n, k);
}
"""
5
1 2 1 3 4
2 //k
4 //sub arrays count
"""
```

###  Find All Subarrays with Zero Sum
* Problem: Count the number of subarrays whose sum is equal to 0.
* Example:
* Input: [4, -1, -3, 1, 2, -2, -1]
* Output: 5

```
#include<stdio.h>
#include<stdbool.h>
bool check(int arr[], int s, int e){
    int sum=0;
    for(int i=s; i<=e; i++){
        sum+=arr[i];
    }
    if(sum==0){
        return true;
    }
    else{
        return false;
    }
}
void find(int arr[], int n){
    int count=0;
    for(int i=0; i<n; i++){
        for(int j=i+1; j<n; j++){
           if(check(arr,i,j)){
               count++;
           }
        }
    }
   printf("%d", count);
}
int main(){
    int n;
    scanf("%d", &n);
    int arr[100];
    for(int i=0; i<n; i++){
        scanf("%d", &arr[i]);
    }
    find(arr, n);
}
""
7
4 -1 -3 1 2 -2 -1
5 //sub arrays count whse sum is equal to 0
"""
```
