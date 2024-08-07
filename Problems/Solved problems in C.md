### Print even indexed strings:

```
#include<stdio.h>
#include<string.h>
int main(){
    int n;
    scanf("%d", &n);
    char str[n][100];
    for(int i=0; i<n; i++){
        scanf("%s", str[i]);
    }
    for(int j=0; j<n; j++){
        if(j%2==0){
            printf("%s ", str[j]);
        }
    }
    return 0;
}
```

### First repeating char with its frequency:

```
#include<stdio.h>
#include<string.h>
int main(){
    char str[255];
    fgets(str, 255, stdin);
    int l=strlen(str);
    int count=0;
        for(int i=0; i<l; i++){
            count=1;
            for(int j=i+1; j<l; j++){
                if(str[i]==str[j] && str[i]!='\n' && str[i]!=' '){
                    count++;
                }
            }
            if(count>1){
                printf("%c %d\n", str[i], count);
                break;
            }
        }
    return 0;
}
```

### split and print the phone number, gender, age, seat:

```
#include<stdio.h>
#include<string.h>
int main(){
    int n;
    scanf("%d", &n);
    char records[n][100];
    
    for(int i=0; i<n; i++){
        scanf("%s", records[i]);
    }
    
    for(int i=0; i<n; i++){
        char phone[11], gender, age[3], seat[3];
        
        strncpy(phone, records[i], 10);
        phone[10]='\0';
        
        gender = records[i][10];
        
        strncpy(age, &records[i][11], 2);
        age[2]='\0';
        
        strncpy(seat, &records[i][13], 2);
        seat[2]='\0';
        
        printf("Record: %d\n", i+1);
        printf("phone number: %s\n", phone);
        printf("gender: %c\n", gender);
        printf("age: %s\n", age);
        printf("seat: %s\n", seat);
    }
    return 0;
}
```

### Find the maximum of a character in a given string .Igore the case(lower or upper case).Return the character in lower case Input:Test  Output:t

```
#include<stdio.h>
#include<string.h>
#include<ctype.h>
int main(){
    char str[255];
    fgets(str, 255, stdin);
    str[strcspn(str, "\n")]='\0';
    char maxChar = str[0];
    int l=strlen(str);
    for(int i=0; i<l; i++){
        if(str[i]>maxChar){
            maxChar=str[i];
        }
    }
    printf("%c", tolower(maxChar));
    return 0;
}
```

### Print the given string without alphabets:
```
#include<stdio.h>
#include<string.h>
#include<ctype.h>
int main(){
    char str[255];
    fgets(str, 255, stdin);
    str[strcspn(str, "\n")]='\0';
    int i=0;
    while(str[i]!='\0'){
        if(!(str[i]>='a' && str[i]<='z') || (str[i]>='A' && str[i]<='Z')){
            printf("%c", str[i]);
        }
        i++;
    }
    return 0;
}
```

### Print the first non-repeating char in the string:

```
#include<stdio.h>
#include<string.h>
#include<ctype.h>
int main(){
    char str[255];
    fgets(str, 255, stdin);
    str[strcspn(str, "\n")]='\0';
    int l=strlen(str);
    int count=0;
    for(int i=0; i<l; i++){
        count=1;
        for(int j=i+1; j<l; j++){
            if(str[i]==str[j]){
                count++;
            }
        }
        if(count==1){
            printf("%c", str[i]);
            break;
        }
    }
    
    return 0;
}
```

### Find the length between two words:

```
#include<stdio.h>
#include<string.h>
#include<ctype.h>
int main(){
    char str[255];
    fgets(str, 255, stdin);
    str[strcspn(str, "\n")]='\0';
    int l=strlen(str);
    int lencount=0;
    int in_wrd=0;
    for(int i=0; i<l; i++){
        if(isspace(str[i])){
            lencount++;
        }
        else{
            if(!in_wrd){
                in_wrd=1;
            }
        }
    }
    printf("%d", lencount);
       
    
    return 0;
}
```

### Remove dplicates:

```
#include<stdio.h>
#include<string.h>
int main(){
    char str[255];
    fgets(str, 255, stdin);
    int l=strlen(str);
    int i=0;
    while(str[i]!='\0'){
    for(int i=0; i<l; i++){
        if(str[i]!='\0' && str[i]!=' '){
        for(int j=i+1; j<l; j++){
            if(str[i]==str[j]){
                str[j]='\0';
            }
        }
        }
    }
    i++;
    }
    for(int i=0; i<l; i++){
        if(str[i]!='\0'){
            printf("%c", str[i]);
        }
    }
    return 0;
}
```

### Print consecutive repeated characters:

```
#include <stdio.h>
#include <string.h>

int main() {
    char str[255];
    fgets(str, 255, stdin);
    int i=0;
    int l=strlen(str);
    if(str[l-1]=='\n'){
        str[l-1]='\0';
        l--;
    }
    
    for(int i=0; i<l; i++){
        if(str[i]==str[i-1]){
            printf("%c", str[i]);
        }
    }

    return 0;
}
```
### Check the given strings are Isomorphic:
```
#include <stdio.h>
#include <string.h>
#include<stdbool.h>

char areIsomorphic(char *str1, char *str2){
    int l=strlen(str1);
    if(strlen(str2)!=l){
        return false;
    }
    int m1[256]={0};
    int m2[256]={0};
    
    for(int i=0; i<l; i++){
        if(m1[(unsigned char) str1[i]] != m2[(unsigned char) str2[i]]){
            return false;
        }
        m1[(unsigned char) str1[i]] = i+1;
        m2[(unsigned char) str2[i]] = i+1;
    }
    return true;
}

int main() {
    char str1[255];
    char str2[255];
    fgets(str1, 255, stdin);
    fgets(str2, 255, stdin);
    int l=strlen(str1);
    int m=strlen(str2);
    if(str1[l-1]=='\n'){
        str1[l-1]='\0';
        l--;
    }
    if(str2[m-1]=='\n'){
        str2[m-1]='\0';
        m--;
    }
    if(areIsomorphic(str1, str2)){
        printf("yes\n");
    }
    else{
        printf("No");
    }
    return 0;
}
```

### Print odd indexed characters in reverse order:

```
#include<stdio.h>
#include<string.h>
#include<stdbool.h>
int main(){
    char str[255];
    fgets(str, 255, stdin);
    int l=strlen(str);
    if(str[l-1]=='\n'){
        str[l-1]='\0';
        l--;
    }
    for(int i=l-1; i>=0; i--){
        if(i%2==0){
            printf("%c ", str[i]);
        }
    }

    return 0;
}
```




