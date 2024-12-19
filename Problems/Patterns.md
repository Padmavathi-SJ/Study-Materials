## Pattern printing

### 1. hallo pattern
```
#include<stdio.h>
int main(){
    int n=5;
    for(int i=1; i<=n; i++){
        for(int s=1; s<=n-i; s++){
            printf(" ");
        }
        for(int j=1; j<=i; j++){
            if(i==1 || i==n || j==i || j==1){
                printf("*");
            }
            else{
                printf(" ");
            }
        }
        printf("\n");
    }
    
}

"""
    *
   **
  * *
 *  *
*****
"""
```
