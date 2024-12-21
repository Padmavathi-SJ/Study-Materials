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

### zigzag
```
#include<stdio.h>
void main(){
    int N=6;
    int startVal=1;
    int endVal=0;
    for(int i=1; i<=N; i++){
            if(i%2==0){
                startVal+=2;
                printf("%d ", startVal);
            }
            else{
                printf("%d ", startVal);
            }
            //middlepart
            for(int k=1; k<=N; k++){
                printf("%d ", i);
            }
            if(i%2==0){
                printf("%d ", endVal);
            }
            else{
                endVal+=2;
                printf("%d ", endVal);
            }
            printf("\n");
        }
}
"""
1 1 1 1 1 1 1 2 
3 2 2 2 2 2 2 2 
3 3 3 3 3 3 3 4 
5 4 4 4 4 4 4 4 
5 5 5 5 5 5 5 6 
7 6 6 6 6 6 6 6 
"""
```

### reverse pramid
```
#include<stdio.h>
void main(){
    int N=6;
    int index=0;
    int imp=43;
    int num=1;
    
    for(int i=1; i<=N; i++){
        //Space
        for(int s=1; s<i; s++){
            printf("  ");
        }
            for(int k=N; k>=i; k--){
                printf("%02d ", num);
            num++;
            }
            index+=2;
            
            int t=imp-1-(N-i);
            imp=t;
            
            for(int m=N; m>=i; m--){
                printf("%d ", t);
                t++;
            }
            printf("\n");
        }
}
"""
01 02 03 04 05 06 37 38 39 40 41 42 
  07 08 09 10 11 32 33 34 35 36 
    12 13 14 15 28 29 30 31 
      16 17 18 25 26 27 
        19 20 23 24 
          21 22 
"""
```
