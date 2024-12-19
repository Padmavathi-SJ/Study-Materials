## recursion 

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
