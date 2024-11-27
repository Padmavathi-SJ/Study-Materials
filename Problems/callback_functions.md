### 1. program to print the square of array elements using callback function.
```
#include<stdio.h>
void process(int arr[], int n, int(*callback)(int)){
    for(int i=0; i<n; i++){
        arr[i]=callback(arr[i]);
    }
}
int square(int n){
    return n*n;
}

int main() {
    int n;
    scanf("%d", &n);
    int arr[n];
    for(int i=0; i<n; i++){
        scanf("%d", &arr[i]);
    }
    process(arr, n, square);
    for(int i=0; i<n; i++){
        printf("%d ", arr[i]);
    }
    return 0;
}
"""
5
1 2 3 4 5
1 4 9 16 25
"""
```
