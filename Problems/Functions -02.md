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
