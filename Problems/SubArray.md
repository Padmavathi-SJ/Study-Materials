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
  
### Sub array with equal zeros and ones
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
