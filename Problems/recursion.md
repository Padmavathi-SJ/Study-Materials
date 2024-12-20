## recursion 

### even nums in range using recursion
``` 
#include<stdio.h>
void find(int start, int end){
    if(start > end){
        return; //base case
    }
    if(start%2==0){
    printf("%d ", start);
    }
    find(start+1, end);
}
void main(){
    int start;
    scanf("%d", &start);
    int end;
    scanf("%d", &end);
    find(start, end);
    
}
"""
1
10
2 4 6 8 10
"""
```

### odd nums in range using recursion
``` 
#include<stdio.h>
void find(int start, int end){
    if(start > end){
        return; //base case
    }
    if(start%2!=0){
    printf("%d ", start);
    }
    find(start+1, end);
}
void main(){
    int start;
    scanf("%d", &start);
    int end;
    scanf("%d", &end);
    find(start, end);
    
}
"""
1
10
1 3 5 7 9
"""
```

### print 10 natural nums from 1
```
#include<stdio.h>
void find(int n){
   if(n<=10){
       printf("%d ", n);
       find(n+1);
   }
}
void main(){
    int n;
    scanf("%d", &n);
    find(n);
}
"""
1
1 2 3 4 5 6 7 8 9 10
"""
```

### fibonacci series upto n
```
#include<stdio.h>
int fib(int n){
   if(n==0){
       return 0;
   }
   else if(n==1){
       return 1;
   }
   else{
       return fib(n-1)+fib(n-2);
   }
}
void main(){
    int n;
    scanf("%d", &n);
    int i=1;
    int num=0;
    while(num < n){
        num=fib(i);
        if(num<n){
        printf("%d ", num);
        }
        i++;
    }
    
}
"""
10
1 1 2 3 5 8
"""
```