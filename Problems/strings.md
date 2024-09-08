### 01. Print even indexed strings:

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

### 02. First repeating char with its frequency:

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

### 03. split and print the phone number, gender, age, seat:

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

### 04. Find the maximum of a character in a given string .Igore the case(lower or upper case).Return the character in lower case Input:Test  Output:t

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

### 05. Print the given string without alphabets:
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

### 06. Print the first non-repeating char in the string:

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

### 07. Find the length between two words:

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

### 08. Remove dplicates:

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

### 09. Print consecutive repeated characters:

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
### 10. Check the given strings are Isomorphic:
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

### 11. Print odd indexed characters in reverse order:

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

### 12. Reverse the words in the string:

```
#include<stdio.h>
#include<string.h>
int main(){
    char str[255];
    fgets(str, 255, stdin);
    int l=strlen(str);
    if(str[l-1]=='\n'){
        str[l-1]='\0';
        l--;
    }
    char reversed[255];
    int m=0;
    int end=l-1;
    for(int i=l-1; i>0; i--){
        if(str[i]==' ' || str[i]=='\t' || str[i]=='\n'){
            int start=i+1;
            for(int k=start; k<=end; k++){
                reversed[m++]=str[k];
            }
            reversed[m++]=' ';
            end=i-1;
            
        }
    }
    for(int i=0; i<=end; i++){
        reversed[m++]=str[i];
    }
    reversed[m]='\0';
    printf("%s", reversed);
    return 0;
}
```

### 13. count characters of the words present in the string:

```
#include<stdio.h>
#include<string.h>
int main(){
    char str[255];
    fgets(str, 255, stdin);
    int l=strlen(str);
    if(str[l-1]=='\n'){
        str[l-1]='\0';
        l--;
    }
    char reversed[255];
    int m=0;
    int end=l-1;
    for(int i=l-1; i>0; i--){
        if(str[i]==' ' || str[i]=='\t' || str[i]=='\n'){
            int start=i+1;
            int count=0;
            for(int k=start; k<=end; k++){
                reversed[m++]=str[k];
                count++;
            }
            printf("%d ", count);
            reversed[m++]=' ';
            end=i-1;
        }
    }
    int count=0;
    for(int i=0; i<=end; i++){
        reversed[m++]=str[i];
        count++;
    }
    printf("%d\n", count);
    reversed[m]='\0';
    printf("%s\n", reversed);
    
    
    return 0;
}
```

### 14. check whether the word is present in the given string:
```
#include<stdio.h>
#include<string.h>

int main(){
    char str[255];
    fgets(str, 255, stdin);
    int l = strlen(str);
    if(str[l-1] == '\n'){
        str[l-1] = '\0';
        l--;
    }

    char choice[255];
    fgets(choice, 255, stdin);
    int m = strlen(choice);
    if(choice[m-1] == '\n'){
        choice[m-1] = '\0';
        m--;
    }

   int found=0;
   
   for(int i=0; i<=l-m; i++){
       int j;
       for(j=0; j<m; j++){
           if(str[i+j]!=choice[j]){
               break;
           }
       }
       if(j==m){
           found=1;
           break;
       }
   }

    if(found){
        printf("Yes, the choice is a subword in the string!\n");
    } else {
        printf("No, the choice is not a subword in the string!\n");
    }

    return 0;
}
```

### 15. Remove spaces:
```
#include<stdio.h>
#include<string.h>
int main(){
    char str[255];
    fgets(str, 255, stdin);
    int l=strlen(str);
    if(str[l-1]=='\n'){
        str[l-1]='\0';
        l--;
    }
    int i,j=0;
    while(str[i]!='\0'){
        if(str[i]!=' '){
            str[j++]=str[i];
        }
        i++;
    }
    str[j]='\0';
    printf("%s", str);
    return 0;
}
```

### 16. Remove duplicate characters
```
#include<stdio.h>
#include<string.h>
int main(){
    char str[255];
    fgets(str, 255, stdin);
    int l=strlen(str);
    if(str[l-1]=='\n'){
        str[l-1]='\0';
        l--;
    }
    char new[255];
    int m=0;
    for(int i=0; i<l; i++){
        if(str[i]!='\0'){
        for(int j=i+1; j<l; j++){
            if(str[i]==str[j]){
                str[j]='\0';
            }
        }
        new[m++]=str[i];
        }
    }
    new[m]='\0';
    printf("%s", new);
    return 0;
}
```

### 17. count of words
```
#include<stdio.h>
#include<string.h>
#include<ctype.h>
int main(){
    char str[255];
    fgets(str, 255, stdin);
    int l=strlen(str);
    if(str[l-1]=='\n'){
        str[l-1]='\0';
        l--;
    }
   int in_wrd=0;
   int count=0;
   for(int i=0; i<l; i++){
       if(isspace(str[i])){
           in_wrd=0;
       }
       else if(!in_wrd){
           count++;
           in_wrd=1;
       }
   }
    printf("%d", count);
    return 0;
}
```

### 18. Concatenate two strings without using 'strcat' function
```
#include<stdio.h>
#include<string.h>
#include<ctype.h>
int main(){
    char str1[255];
    fgets(str1, 255, stdin);
    int l=strlen(str1);
    char str2[255];
    fgets(str2, 255, stdin);
    int m=strlen(str2);
    if(str1[l-1]=='\n'){
        str1[l-1]='\0';
        l--;
    }
    if(str2[m-1]=='\n'){
        str2[m-1]='\0';
        m--;
    }
    str1[l++]=' ';
    for(int i=0; i<m; i++){
        str1[l++]=str2[i];
    }
    str1[l]='\0';
    printf("%s", str1);
    return 0;
}
```
### 19. concatenate two strings
```
#include<stdio.h>
#include<string.h>
#include<ctype.h>
int main(){
    char str1[255];
    fgets(str1, 255, stdin);
    int l=strlen(str1);
    char str2[255];
    fgets(str2, 255, stdin);
    int m=strlen(str2);
    if(str1[l-1]=='\n'){
        str1[l-1]='\0';
        l--;
    }
    if(str2[m-1]=='\n'){
        str2[m-1]='\0';
        m--;
    }

    strcat(str1, str2);
    printf("%s", str1);
    return 0;
}
```

### 20. Compare two string 
```
#include<stdio.h>
#include<string.h>
int main(){
    char s[]="padma";
    char t[]="paadmaa";
    int isequal=1;
    for(int i=0; s[i]!='\0'; i++){
    if(s[i]!=t[i]){
        isequal=0;
        break;
    }
        }
        
    if(isequal){
        printf("yes equal\n");
    }
    else{
        printf("not equal");
    }
    return 0;
}

(or)

#include<stdio.h>
#include<string.h>
int main(){
    char s[]="padma";
    char t[]="padma";
    if(strcmp(s, t)==0){
        printf("Yes equal\n");
    }
    else{
        printf("not equal");
    }
    return 0;
}
```

### 21. Remove specific char from a string:
```
#include<stdio.h>
#include<string.h>
int main(){
    char s[]="padma";
    char ch='d';
    int j=0;
    for(int i=0; s[i]!='\0'; i++){
        if(s[i]!=ch){
            s[j++]=s[i];
        }
    }
    s[j]='\0';
    printf("%s", s);
    return 0;
}
```

### 22. First non-repeating char
```
#include<stdio.h>
#include<string.h>
int main(){
    char s[100]="padmavathi";
    int freq[255]={0};
    for(int i=0; s[i]!='\0'; i++){
        freq[s[i]]++;
    }
    
    for(int i=0; s[i]!='\0'; i++){
        if(freq[s[i]]==1){
            printf("%c", s[i]);
            break;
        }
    }
    return 0;
}
```

### 23. Finding substring
```
#include<stdio.h>
#include<string.h>

int main(){
    char s[100]="this is padma";
    char t[100]="is";
    if(strstr(s, t)){
        printf("Yes\n");
    }
    else{
        printf("No\n");
    }
    return 0;
}

(or)

#include<stdio.h>
#include<string.h>

int substring(char s[], char t[]){
    int j;
    for(int i=0; s[i]!='\0'; i++){
        for(j=0; t[j]!='\0'; j++){
            if(s[i+j]!=t[j]){
                break;
            }
        }
        if(t[j]=='\0'){
            return 1;
        }
    }
    return 0;
}

int main(){
    char s[100]="this is padma";
    char t[100]="isd";
    if(substring(s, t)){
        printf("Yes\n");
    }
    else{
        printf("No\n");
    }
    return 0;
}
```

### 24. string to int

```
#include<stdio.h>
#include<stdlib.h>

int main(){
    char s[]="1232";
    int num=atoi(s);
    printf("%d", num);
    
    return 0;
}
```

### 25. int to string

```
#include<stdio.h>
#include<stdlib.h>

int main(){
   int num=123;
   char s[100];
   sprintf(s, "%d", num);
   printf("%s", s);
    
    return 0;
}
```
### 26. first non-repeating char
```
#include<stdio.h>
#include<string.h>
int main(){
    char s[255];
    fgets(s, 255, stdin);
    int l=strlen(s);
    if(s[l-1]=='\n'){
        s[l-1]='\0';
        l--;
    }
    int count=0;
    char new[255];
    int m=0;
    for(int i=0; i<l; i++){
        count=1;
        for(int j=i+1; j<l; j++){
            if(s[i]==s[j]){
                count++;
            }
        }
        if(count==1){
            new[m++]=s[i];
        }
    }
    new[m]='\0';
    printf("%c", new[0]);
    //printf("%s", new);
    // printf("%c", new[m-1]);
    return 0;
}
```

### 27. anagrams:

```
#include<stdio.h>
#include<string.h>
#include<stdbool.h>

char isAnagram(char s[], char t[]){
    if(strlen(s)!=strlen(t)){
        return false;
    }
    int count1[256]={0};
    int count2[256]={0};
    
    for(int i=0; s[i]!='\0'; i++){
        count1[s[i]]++;
    }
    
    for(int i=0; t[i]!='\0'; i++){
        count2[t[i]]++;
    }
    
    for(int i=0; i<256; i++){
        if(count1[i]!=count2[i]){
            return 0;
        }
    }
    return 1;
}

int main(){
    char s[100]="god";
    char t[100]="don";
    if(isAnagram(s,t)){
        printf("Yes\n");
    }
    else {
        printf("No\n");
    }
    return 0;
}
```

### 28. convert firts char of each word to uppercase
```
#include<stdio.h>
#include<string.h>
#include<ctype.h>

int main(){
    char s[255]="this is padma";
    int l=strlen(s);
    if(s[l-1]=='\n'){
        s[l-1]='\0';
        l--;
    }
    
    int in_wrd=1;
    for(int i=0; i<l; i++){
        if(isspace(s[i])){
        in_wrd=1;
        }
        else if(in_wrd){
            s[i]=toupper(s[i]);
            in_wrd=0;
        }
    }
    printf("%s", s);
    return 0;
}
```

### 29. covert the string to title/sentence case 
```
#include<stdio.h>
#include<string.h>
#include<ctype.h>

int main(){
    char s[255]="tHIS iS pAdMa"; 
    int l=strlen(s);
    if(s[l-1]=='\n'){
        s[l-1]='\0';
        l--;
    }
    
    int in_wrd=1;
    for(int i=0; i<l; i++){
        if(isspace(s[i])){
            in_wrd=1;
        }
        else if(in_wrd){
            s[i]=toupper(s[i]);
            in_wrd=0;
        }
        else{
            s[i]=tolower(s[i]);
        }
    }
    printf("%s", s); //This is Padma
    return 0;
}
```
### 30. First occurance of a char
```
#include<stdio.h>
#include<string.h>
#include<ctype.h>

int main(){
    char s[255]="This is padma"; 
    int l=strlen(s);
    char ch='a';
    for(int i=0; i<l; i++){
        if(s[i]==ch){
            printf("%c is in %dth index", ch, i);
            break;
        }
    }
    return 0;
}
```

### 31. Last occurance of a char
```
#include<stdio.h>
#include<string.h>
#include<ctype.h>

int main(){
    char s[255]="This is padma"; 
    int l=strlen(s);
    char ch='i';
    for(int i=l-1; i>=0; i--){
        if(s[i]==ch){
            printf("%c is in %dth index", ch, i);
            break;
        }
    }
    return 0;
}
```

### 32. Toggle case(convert upper-lower, lower-upper)
**conver upper to lower : +32, convert lower to upper : -32**
```
#include<stdio.h>
#include<string.h>
#include<ctype.h>

int main(){
    char s[255]="tHiS Is PaDmA"; 
    int l=strlen(s);
    for(int i=0; i<l; i++){
        if(s[i]>='a' && s[i]<='z'){
            s[i]=s[i]-32;
        }
        else if(s[i]>='A' && s[i]<='Z'){
            s[i]=s[i]+32;
        }
    }
    printf("%s", s);
    return 0;
}

(or)

#include<stdio.h>
#include<string.h>
#include<ctype.h>

int main(){
    char s[255]="tHiS Is PaDmA"; 
    int l=strlen(s);
    for(int i=0; i<l; i++){
        if(s[i]>='a' && s[i]<='z'){
            s[i]=s[i]-('a'-'A');
        }
        else if(s[i]>='A' && s[i]<='Z'){
            s[i]=s[i]+('a'-'A');
        }
    }
    printf("%s", s);
    return 0;
}
```
### 33. Reverse a string:
```
#include<stdio.h>
#include<string.h>


int main(){
    char s[255]="This is Padma"; 
    int l=strlen(s);
    for(int i=l-1; i>=0; i--){
        printf("%c", s[i]);
    }
    return 0;
}
```
### 34. copy one string to another string
```
#include <stdio.h>
#include<string.h>
int main() {
    char str[100];
    char temp[100];
    fgets(str,sizeof(str),stdin);
    strcpy(temp,str);
    printf("%s",temp);
    return 0;
}
(or)

#include <stdio.h>
int main() {
    char str[100];
    char temp[100];
    fgets(str,sizeof(str),stdin);
   // printf("%s",str);
   int i=0;
   for(int i=0;str[i]!='\0';i++){
       temp[i]=str[i];
   }
    printf("%s",temp);
    return 0;
}
```

### 35. check palindrome or not
```
#include<stdio.h>
#include<string.h>
int main(){
    char s[255]="gog";
    int l=strlen(s);
    if(s[l-1]=='\n'){
        s[l-1]='\0';
        l--;
    }
    int found=1;
    for(int i=0; i<l; i++){
        if(s[i]!=s[l-1-i]){
            found=0;
            break;
        }
    }
    if(found){
        printf("Yes\n");
    }
    else {
        printf("No\n");
    }
    return 0;
}
```
### 36. Length of last word:
```
#include<stdio.h>
#include<string.h>

int main(){
    char s[255]="Hello magic mummy";
    int l=strlen(s);
    int i,count=0;
    int end=l-1;
    for(i=l-1; i>=0; i--){
        if(s[i]==' ' || s[i]== '\t'){
            int start=i+1;
         for(int j=start; j<=end; j++){
             count++;
         }
         break;
        }
    }
    printf("%d", count);
    return 0;
}
```

### 37. Length of first word:
```
#include<stdio.h>
#include<string.h>

int main(){
    char s[255]="Hello magic mummy";
    int l=strlen(s);
    int i,count=0;
    int start=0;
    for(i=0; i<l; i++){
        if(s[i]==' ' || s[i]== '\t'){
            int end=i-1;
         for(int j=start; j<=end; j++){
             count++;
         }
         break;
        }
    }
    printf("%d", count);
    return 0;
}
```

### 38. print even indexed words:
```
#include<stdio.h>
#include<string.h>
#include<ctype.h>
int main(){
    char s[255]="Hi hello good morning";
    int l=strlen(s);
    int i,j;
    char new[255];
    int m=0;
    int WordIndex=0;
    for(int i=0; i<l; i++){
        if(s[i]!=' ' && s[i]!='\t'){
                if(i==0 || s[i-1]==' ' || s[i-1]=='\t'){
                    if(WordIndex%2==0){
                    j=i;
                    while(j<l && s[j]!=' ' && s[j]!='\t'){
                        new[m++]=s[j];
                        j++;
                    }
                    new[m++]=' ';
                }
            WordIndex++;
            }
        }
    }
    new[m]='\0';
    printf("%s", new);
    return 0;
}
```

### 39. print odd indexed words:
```
#include<stdio.h>
#include<string.h>
#include<ctype.h>
int main(){
    char s[255]="Hi mummy how are you";
    int l=strlen(s);
    int i,j;
    char new[255];
    int m=0;
    int wordIndex=0;
    for(int i=0; i<l; i++){
        if(s[i]!=' ' && s[i]!='\t'){
            if(i==0 || s[i-1]==' ' || s[i-1]=='\t'){
                if(wordIndex%2!=0){
                    j=i;
                    while(j<l && s[j]!=' ' && s[j]!='\t'){
                        new[m++]=s[j];
                        j++;
                    }
                    new[m++]=' ';
                }
                wordIndex++;
            }
        }
    }
    new[m]='\0';
    printf("%s", new);
    return 0;
}
```
### 40. count of even indexed words
```
#include<stdio.h>
#include<string.h>
#include<ctype.h>
int main(){
    char s[255]="Hi mummy how are you love you mummy bye";
    int l=strlen(s);
    int i, j;
    char new[255];
    int m=0,count=0;
    int wordIndex=0;
    for(int i=0; i<l; i++){
        if(s[i]!=' ' && s[i]!='\t'){
            if(i==0 || s[i-1]==' ' || s[i-1]=='\t'){
                if(wordIndex%2==0){
                    j=i; 
                    while(j<l && s[j]!=' ' && s[j]!='\t'){
                        new[m++]=s[j];
                        j++;
                    }
                    new[m++]=' ';
                    count++;
                }
                wordIndex++;
            }
        }
    }

    printf("%d", count);
    return 0;
}
```

### 41. count of odd indexed words:
```
#include<stdio.h>
#include<string.h>
#include<ctype.h>
int main(){
    char s[255]="Hi mummy how are you love you mummy bye";
    int l=strlen(s);
    int i, j;
    char new[255];
    int m=0,count=0;
    int wordIndex=0;
    for(int i=0; i<l; i++){
        if(s[i]!=' ' && s[i]!='\t'){
            if(i==0 || s[i-1]==' ' || s[i-1]=='\t'){
                if(wordIndex%2!=0){
                    j=i; 
                    while(j<l && s[j]!=' ' && s[j]!='\t'){
                        new[m++]=s[j];
                        j++;
                    }
                    new[m++]=' ';
                    count++;
                }
                wordIndex++;
            }
        }
    }

    printf("%d", count);
    return 0;
}
```
### 42. check whether a string is subsequence of another string:

```
#include<stdio.h>
#include<string.h>
#include<stdbool.h>

bool isSubsequence(char s[], char t[]){
    int l=strlen(s);
    int m=strlen(t);
    int j=0;
    for(int i=0; i<l && j<m; i++){
        if(s[i]==t[j]){
            j++;
        }
    }
    return j==m;
}

int main(){
    char s[100]="adbec";
    char t[100]="abc";
    
    if(isSubsequence(s,t)){
        printf("Yes\n");
    }
    else {
        printf("No\n");
    }
    return 0;
}
```
### 43. 392. Is Subsequence

**Given two strings s and t, return true if s is a subsequence of t, or false otherwise.
A subsequence of a string is a new string that is formed from the original string by deleting some (can be none) of the characters without disturbing the relative positions of the remaining characters. (i.e., "ace" is a subsequence of "abcde" while "aec" is not).**

**using java**

```
bool isSubsequence(char* s, char* t) {
   int length = strlen(s);
    if (length == 0) return true;

    int c = 0;
    int t_length = strlen(t);

    for (int i = 0; i < t_length && c < length; i++) {
        if (t[i] == s[c]) {
            c++;
        }
    }

    return c == length;
}
```
### 44. print odd postion words
**using c**

```
#include<stdio.h>
#include<string.h>


int main() {
    char str[100][100];
    int n;
    
    // Input number of words
    scanf("%d", &n);
    
    // Input words
    for(int i = 0; i < n; i++) {
        scanf("%s", str[i]);
    }
    
    // Process and print words at odd indices
    for(int i = 0; i < n; i++) {
        if(i % 2 == 0) { // check if index is even
            printf("%s ", str[i]);
        }
    }
    
    return 0;
}
```

### 45.  print even postion words:

**using c**

```
#include<stdio.h>
#include<string.h>
int main() {
    char str[100][100];
    int n;
    
    // Input number of words
    scanf("%d", &n);
    
    // Input words
    for(int i = 0; i < n; i++) {
        scanf("%s", str[i]);
    }
    
    // Process and print words at odd indices
    for(int i = 0; i < n; i++) {
        if(i % 2 != 0) { // check if index is even
            printf("%s ", str[i]);
        }
    }
    
    return 0;
}
```

### 46. print the words between a range given by user

```
#include<stdio.h>
#include<string.h>


int main() {
    char str[100][100];
    int n;
    scanf("%d", &n);
    for(int i = 0; i < n; i++) {
        scanf("%s", str[i]);
    }
    int start=2;
    int end=5;
    int len = strlen(str);
    for(int i=start; i<end; i++){

            printf("%s ", str[i]);

    }
    return 0;
}
```

**output: 7
          Hi I am cs student from BIT
          am cs student**

### 47. check whether the given string is pangram or not?
**Pangram - every alphabet must present in the string atleaset for one time**

```
#include<stdio.h>
#include<string.h>
#include<ctype.h>
#include<stdbool.h>
bool isPangram(char str[]){
    bool alphabet[26]={false};
    int index;
    
    for(int i=0; str[i]!='\0'; i++){
        if(isalpha(str[i])){
            index=tolower(str[i]) - 'a';
            alphabet[index]=true;
        }
    }
    
    for(int i=0; i<26; i++){
        if(alphabet[i]==false){
            return false;
            break;
            
        }
    }
    return true;
}
int main(){
    char str[255];
    fgets(str, 255, stdin);
    if(isPangram(str)){
        printf("Yes\n");
    }
    else {
        printf("No");
    }
    return 0;
}
```
### 48. 

**input:
3
ABCDE
EDCBA
ROUND
RINGS
START
STUNT**

**output:
BBGBB
GBBBB
GGBBG**

```
#include <stdio.h>
#include<string.h>

int main(void) {
	int t;
	scanf("%d", &t);
	getchar();
	while(t>0){
	char s[100], t[100];
	fgets(s, 100, stdin);
	fgets(t, 100, stdin);
	int l=strlen(s);
	int n=strlen(t);
	if(s[l-1]=='\n'){
	    s[l-1]='\0';
	    l--;
	}
	if(t[n-1]=='\n'){
	    t[n-1]='\0';
	    n--;
	}
	char m[100];
	int x=0;
	for(int i=0; s[i]!='\0'; i++){
	    if(s[i]==t[i]){
	        m[x++]='G';
	    }
	    else{
	        m[x++]='B';
	    }
	}
	m[x]='\0';
	printf("%s\n", m);
	t--;
	}
	return 0;
}
```
### 49. Find all occurances of word:
```
#include<stdio.h>
#include<string.h>
#include<ctype.h>
int main() {
    int n;
    scanf("%d", &n);
    char str[n][100];
    for(int i=1; i<=n; i++){
        scanf("%s", str[i]);
    }
    getchar();
    char choice[100];
    fgets(choice, 100, stdin);
    
    choice[strcspn(choice, "\n")]='\0';
    int m=strlen(choice);
    for(int i=1; i<=n; i++){
        int len=strlen(str[i]);
        if(len==m){
            if(strcmp(str[i], choice)==0) {
                printf("%d ", i);
            }
        }
    }
    return 0;
}
```
### 50. Find 1st occurance of word
```
#include<stdio.h>
#include<string.h>
#include<ctype.h>
int main() {
    int n;
    scanf("%d", &n);
    char str[n][100];
    for(int i=1; i<=n; i++){
        scanf("%s", str[i]);
    }
    getchar();
    char choice[100];
    fgets(choice, 100, stdin);
    
    choice[strcspn(choice, "\n")]='\0';
    int m=strlen(choice);
    for(int i=1; i<=n; i++){
        int len=strlen(str[i]);
        if(len==m){
            if(strcmp(str[i], choice)==0) {
                printf("%d", i);
                break;
            }
        }
    }
    return 0;
}
```

### 51. Find last occurance of word:
```
#include<stdio.h>
#include<string.h>
#include<ctype.h>
int main() {
    int n;
    scanf("%d", &n);
    char str[n][100];
    for(int i=1; i<=n; i++){
        scanf("%s", str[i]);
    }
    getchar();
    char choice[100];
    fgets(choice, 100, stdin);
    
    choice[strcspn(choice, "\n")]='\0';
    int m=strlen(choice);
    for(int i=n; i>=1; i--){
        int len=strlen(str[i]);
        if(len==m){
            if(strcmp(str[i], choice)==0) {
                printf("%d", i);
                break;
            }
        }
    }
    return 0;
}
```
### 52. Find frequency of each word present in the given string
```
#include<stdio.h>
#include<string.h>
#include<ctype.h>
int main() {
    int n;
    scanf("%d", &n);
    char str[n][100];
    for(int i=0; i<n; i++){
        scanf("%s", str[i]);
    }
    int freqOfWrd[n];
    int index=0;
    for(int i=0; i<n; i++){
        int len=strlen(str[i]);
       freqOfWrd[index++]=len;
    }
    for(int i=0; i<index; i++){
        printf("%d ", freqOfWrd[i]);
    }
    return 0;
}
```
### 53. remove all occurance of word
```
#include<stdio.h>
#include<string.h>
#include<ctype.h>
int main() {
    int n;
    scanf("%d", &n);
    char str[n][100];
    for(int i=0; i<n; i++){
        scanf("%s", str[i]);
    }
    getchar();
    char choice[100];
    fgets(choice, 100, stdin);
    choice[strcspn(choice, "\n")]='\0';
    int m=strlen(choice);
    for(int i=0; i<n; i++){
        int len=strlen(str[i]);
        if(len!=m){
            //if(!strcmp(str[i], choice)==0){
                printf("%s ", str[i]);
            }
            
        }
    
    return 0;
}
```

### 54. spliting words from a string using "strtoken"
```
#include<stdio.h>
#include<string.h>
int main(){
    char str[256];
    fgets(str, 256, stdin);
    char *words[100];
    char *word;
    int i=0;
    
    word=strtok(str, " ");
    
    while(word !=NULL){
        words[i]=word;
        i++;
        word=strtok(NULL, " ");
    }
    for(int j=0; j<i; j++){
        if(j%2!=0){
        printf("%s\n", words[j]);
    }
    }
    return 0;
}
```
### 55. length of each word in given string
```
#include<stdio.h>
#include<string.h>
int main(){
    char str[256];
    fgets(str, 256, stdin);
    //str[strcspn(str, "\n")]='\0';
    char *words[100];
    char *word;
    int ind=0;
    word=strtok(str, " ");
    while(word!=NULL){
        words[ind]=word;
        ind++;
        word=strtok(NULL, " ");
    }
    for(int i=0; i<ind; i++){
        int len=strlen(words[i]);
        printf("%d ", len);
    }
    return 0;
}
```
### 56. spliting wordsaccording to "#"
```
#include<stdio.h>
#include<string.h>
int main(){
    char str[256];
    fgets(str, 256, stdin);
    str[strcspn(str, "\n")]='\0';
    
    char *words[100];
    char *word;
    int index=0;
    
    word=strtok(str, "#");
    while(word!=NULL){
        words[index]=word;
        index++;
    word=strtok(NULL, "#");
    }
    // int space=1;
    for(int i=0; i<index; i++){
       // if(!space){
        //printf(" ")}
        
        printf("%s\n", words[i]);
        //space=0;
    }
    return 0;
}
```
### 57. Remove all occurances of word:
```
#include<stdio.h>
#include<string.h>
int main(){
    char str[256];
    fgets(str, 256, stdin);
    str[strcspn(str, "\n")]='\0';
    
    char choice[100];
    scanf("%s", choice);
    
    char *words[100];
    char *word;
    char *temp="dummy";
    
    word=strtok(str, " ");
    int index=0;
    while(word!=NULL){
        words[index]=word;
        index++;
    word=strtok(NULL, " ");
    }
    
    for(int i=0; i<index; i++){
        if(strcmp(words[i], choice)==0){
            words[i]="dummy";
        }
    }
    
    int space=1;
    for(int i=0; i<index; i++){
        if(strcmp(words[i], temp)!=0){
            if(!space){
                printf(" ");
            }
            printf("%s", words[i]);
            space=0;
        }
    }
    
    
    return 0;
}
```
### 58. Remove first occurance of word:
```
#include<stdio.h>
#include<string.h>
int main(){
    char str[256];
    fgets(str, 256, stdin);
    str[strcspn(str, "\n")]='\0';
    
    char choice[100];
    scanf("%s", choice);
    
    char *words[100];
    char *word;
    char *temp="dummy";
    
    word=strtok(str, " ");
    int index=0;
    while(word!=NULL){
        words[index]=word;
        index++;
    word=strtok(NULL, " ");
    }
    
    for(int i=0; i<index; i++){
        if(strcmp(words[i], choice)==0){
            words[i]="dummy";
            break;
        }
    }
    
    int space=1;
    for(int i=0; i<index; i++){
        if(strcmp(words[i], temp)!=0){
            if(!space){
                printf(" ");
            }
            printf("%s", words[i]);
            space=0;
        }
    }
    
    
    return 0;
}
```
### 58. Remove last occurance of word
```
#include<stdio.h>
#include<string.h>
int main(){
    char str[256];
    fgets(str, 256, stdin);
    str[strcspn(str, "\n")]='\0';
    
    char choice[100];
    scanf("%s", choice);
    
    char *words[100];
    char *word;
    char *temp="dummy";
    
    word=strtok(str, " ");
    int index=0;
    while(word!=NULL){
        words[index]=word;
        index++;
    word=strtok(NULL, " ");
    }
    
    for(int i=index-1; i>=0; i--){
        if(strcmp(words[i], choice)==0){
            words[i]="dummy";
            break;
        }
    }
    
    int space=1;
    for(int i=0; i<index; i++){
        if(strcmp(words[i], temp)!=0){
            if(!space){
                printf(" ");
            }
            printf("%s", words[i]);
            space=0;
        }
    }
    
    
    return 0;
}
```

### 59. count of words present in a string using "strtok"
```
#include<stdio.h>
#include<string.h>
int main(){
    char str[256];
    fgets(str, 256, stdin);
    str[strcspn(str, "\n")]='\0';
    
    char *words[100];
    char *word;
   // char *temp="dummy";
    
    word=strtok(str, " ");
    int index=0;
    while(word!=NULL){
        words[index]=word;
        index++;
    word=strtok(NULL, " ");
    }
    
    printf("%d", index);
    
    return 0;
}
```
### 60. print odd indexed words from a string
```
#include<stdio.h>
#include<string.h>
int main(){
    char str[256];
    fgets(str, 256, stdin);
    str[strcspn(str, "\n")]='\0';
    
    char *words[100];
    char *word;
   // char *temp="dummy";
    
    word=strtok(str, " ");
    int index=0;
    while(word!=NULL){
        words[index]=word;
        index++;
    word=strtok(NULL, " ");
    }
    
    int space=1;
    for(int i=0; i<index; i++){
        if(i%2==0){
            if(!space){
                printf(" ");
            }
            printf("%s", words[i]);
            space=0;
        }
    }
    
    return 0;
}
```
### 61. print even indexed words from a string:
```
#include<stdio.h>
#include<string.h>
int main(){
    char str[256];
    fgets(str, 256, stdin);
    str[strcspn(str, "\n")]='\0';
    
    char *words[100];
    char *word;
   // char *temp="dummy";
    
    word=strtok(str, " ");
    int index=0;
    while(word!=NULL){
        words[index]=word;
        index++;
    word=strtok(NULL, " ");
    }
    
    int space=1;
    for(int i=0; i<index; i++){
        if(i%2!=0){
            if(!space){
                printf(" ");
            }
            printf("%s", words[i]);
            space=0;
        }
    }
    
    return 0;
}
```
### 62. reverse the words without changing their positions:
```
#include<stdio.h>
#include<string.h>
int main(){
    char str[256];
    fgets(str, 256, stdin);
    str[strcspn(str, "\n")]='\0';
    
    char *words[100];
    char *word;
   // char *temp="dummy";
    
    word=strtok(str, " ");
    int n=0;
    while(word!=NULL){
        words[n]=word;
        n++;
    word=strtok(NULL, " ");
    }
    
    for(int i=0; i<n; i++){
        int len=strlen(words[i]);
    for(int j=len-1; j>=0; j--){
        printf("%c", words[i][j]);
    }
    if(i < n-1){
    printf(" ");
    }
    }
    
    return 0;
}
```
### 63. check whether the string is palindrome or not:
```
#include<stdio.h>
#include<string.h>
#include<stdbool.h>
bool check(char str[]){
    int len=strlen(str);
    for(int i=0; i<len/2; i++){
        if(str[i]!=str[len-1-i]){
            return false;
        }
    }
    return true;
}
int main(){
    char str[256];
    fgets(str, 256, stdin);
    str[strcspn(str, "\n")]='\0';
    
    if(check(str)){
        printf("Yes\n");
    }
    else{
        printf("No\n");
    }
    return 0;
}
```
### print the words between a range
```
#include<stdio.h>
#include<string.h>
int main(){
    char s[100];
    fgets(s, 100, stdin);
    s[strcspn(s, "\n")]='\0';
    
    char start[100];
    scanf("%s", start);
    char end[100];
    scanf("%s", end);
    
    char *words[100];
    char *word;
    int index=0;
    
    word=strtok(s, " ");
    while(word!=NULL){
        words[index]=word;
        index++;
    word=strtok(NULL, " ");
    }
    
    int m=0,n=0;
    for(int i=0; i<index; i++){
        if(strcmp(words[i], start)==0){
        m=i;
        }
        if(strcmp(words[i],end)==0){
        n=i;
        }
    }
    int count=0;
    //char *new[100];
    for(int i=m+1; i<n; i++){
        //new[count]=words[i];
        printf("%s ", words[i]);
        count++;
    }
    printf("\n%d", count);
    return 0;
}
```
### rotate matrix 90 degree:
```
#include<stdio.h>
#include<string.h>
int rotate(int matrix[100][100], int r, int c){
    
    for(int i=0; i<r; i++){
        for(int j=i+1; j<c; j++){
            int temp=matrix[i][j];
            matrix[i][j]=matrix[j][i];
            matrix[j][i]=temp;
        }
    }
    for(int i=0; i<r; i++){
        for(int k=c-1, j=0; j<k; k--, j++){
            int temp=matrix[i][j];
            matrix[i][j]=matrix[i][k];
            matrix[i][k]=temp;
        }
    }
    
}
int main() {
    int r;
    scanf("%d", &r);
    int c;
    scanf("%d", &c);
    int matrix[100][100];
    for(int i=0; i<r; i++){
        for(int j=0; j<c; j++){
            scanf("%d", &matrix[i][j]);
        }
    }
    rotate(matrix, r, c);
    for(int i=0; i<r; i++){
        for(int j=0; j<c; j++){
            printf("%d ", matrix[i][j]);
        }
        printf("\n");
    }
    return 0;
}
```
### Compare versions 
```
#include<stdio.h>
#include<string.h>
int compare(char *v1, char *v2){
    int num1=0;
    int num2=0;
    while(*v1!='\0' || *v2!='\0'){
        
        while(*v1!='\0' && *v1!='.'){
            num1=num1*10+(*v1-'0');
            v1++;
        }
        
        while(*v2!='\0' && *v2!='.'){
            num2=num2*10+(*v2-'0');
                v2++;
            }
            
        if(num1>num2) return 1;
        if(num1<num2) return -1;
        
        if(*v1=='.') v1++;
        if(*v2=='.') v2++;
        
        num1=0;
        num2=0;
    
    }
    return 0;
    }

int main() {
    char v1[100];
    char v2[100];
    scanf("%s", v1);
    scanf("%s", v2);
    int result=compare(v1, v2);
    if(result==0){
        printf("both are equal\n");
    }
    else if(result > 0){
        printf("v1 is greater than v2\n");
    }
    else {
        printf("v1 is less than v2\n");
    }
    return 0;
}
```
### Reverse first and last words:
```
#include<stdio.h>
#include<string.h>
#include<ctype.h>
int main() {
    char str[256];
    fgets(str, 256, stdin);
    str[strcspn(str, "\n")]='\0';
    int len=strlen(str);
    char fi[100];
    int x=0;
    int start=0;
    for(int i=0; i<len; i++){
        if(str[i]==' ' || str[i]=='\t' || str[i]=='\n'){
            int start=0;
            int end=i-1;
            for(int j=end; j>=start; j--){
                fi[x++]=str[j];
            }
            break;
        }
    }
    fi[x++]='\0';
    
    char la[100];
    int y=0;
    for(int i=len-1; i>=0; i--){
        if(str[i]==' ' || str[i]=='\t' || str[i]=='\n'){
            int start=i+1;
            int end=len-1;
            for(int j=end; j>=start; j--){
                la[y++]=str[j];
            }
            break;
        }
    }
    la[y++]='\0';
    printf("%s\n", fi);
    printf("%s", la);
    
    return 0;
}
```
### Find largest and smallest words from a given string
```
#include<stdio.h>
#include<string.h>
int main() {
    char str[256];
    fgets(str, 256, stdin);
    str[strcspn(str, "\n")]='\0';
    
    char *words[100];
    char *word;
    int index=0;
    word=strtok(str, " ");
    
    while(word!=NULL){
        words[index]=word;
        index++;
    word=strtok(NULL, " ");
    }
    
    for(int i=0; i<index; i++){
        for(int j=i+1; j<index; j++){
        if(strlen(words[i]) > strlen(words[j])) {
            char *temp=words[i];
            words[i]=words[j];
            words[j]=temp;
        }
    }
    }
    
    printf("%s\n", words[0]);
    printf("%s", words[index-1]);
    return 0;
}
```
### Reverse the words without changing their positions:
```
#include<stdio.h>
#include<string.h>
#include<stdbool.h>
int main() {
    char str[256];
    fgets(str, 256, stdin);
    int len=strlen(str);
    char reversed[100];
    int m=0;
    int start=0;
    for(int i=0; i<len; i++){
        if(str[i]==' ' || str[i]=='\t' || str[i]=='\n'){
            int end=i-1;
            for(int j=end; j>=start; j--){
                reversed[m++]=str[j];
            }
            reversed[m++]=' ';
            start=i+1;
        }
    }
    
    for(int i=len-1; i>=start; i--){
        reversed[m++]=str[i];
    }
    reversed[m++]='\0';
    //int l2=strlen(reversed);
    printf("%s\n", reversed);
   // printf("%d\n", len);
    //printf("%d", l2);
    return 0;
}
```

### Check anagram or not:
```
#include<stdio.h>
#include<string.h>
#include<stdbool.h>
bool isAnagram(char s1[], char s2[]){
    if(strlen(s1)!=strlen(s2)){
        return false;
    }
    
    bool count1[256]={false};
    bool count2[256]={false};
    
    for(int i=0; s1[i]!='\0'; i++){
        count1[(unsigned char)s1[i]]++;
    }
    for(int i=0; s2[i]!='\0'; i++){
        count2[(unsigned char)s2[i]]++;
    }
    for(int i=0; i<256; i++){
        if(count1[i]!=count2[i]){
            return false;
        }
    }
    return true;
}
int main() {
    char s1[256];
    fgets(s1, 256, stdin);
    char s2[256];
    fgets(s2, 256, stdin);
    s1[strcspn(s1, "\n")]='\0';
    s2[strcspn(s2, "\n")]='\0';
    
    if(isAnagram(s1, s2)){
        printf("Yes\n");
    }
    else {
        printf("No\n");
    }
    return 0;
}
```
### Check whether the string is Palindrome or not
```
#include<stdio.h>
#include<string.h>
#include<stdbool.h>
#include<ctype.h>
bool isPalin(char str[]){
    int len=strlen(str);
    for(int i=0; i<len/2; i++){
        if(str[i]!=str[len-1-i]){
            return false;
            break;
        }
    }
    return true;
}
void preprocess(char str[]){
    char temp[256];
    int j=0;
    int len=strlen(str);
    for(int i=0; i<len; i++){
        if(isalnum(str[i])){
            temp[j++]=tolower(str[i]);
        }
    }
    temp[j]='\0';
    strcpy(str, temp);
}
int main(){
    char str[256];
    fgets(str, 256, stdin);
    str[strcspn(str, "\n")]='\0';
    preprocess(str);
    if(isPalin(str)){
        printf("Yes\n");
    }
    else {
        printf("No\n");
    }
    return 0;
}
```
### print the frequencies of characters in the given string
```
#include<stdio.h>
#include<string.h>
#include<stdbool.h>
#include<ctype.h>
int main() {
    char str[256];
    fgets(str, 256, stdin);
    str[strcspn(str, "\n")]='\0';
    int len=strlen(str);
    int freq=0;
    for(int i=0; i<len; i++){
        if(str[i]!='\0' && str[i]!=' '){
        freq=1;
    for(int j=i+1; j<len; j++){
        if(str[i]==str[j]){
            freq++;
            str[j]='\0';
        }
    }
    printf("%c : %d\n", str[i], freq);
        }
    }
    return 0;
}
```
### Remove leading and trailing spaces:
```
#include<stdio.h>
#include<string.h>
#include<stdbool.h>
#include<ctype.h>
int main(){
    char str[256];
    fgets(str, 256, stdin);
    str[strcspn(str, "\n")]='\0';
    
    char *words[100];
    char *word;
    int index=0;
    word=strtok(str, " ");
    
    while(word!=NULL){
        words[index]=word;
        index++;
    word=strtok(NULL, " ");
    }
    int space=0;
    for(int i=0; i<index; i++){
        if(space){
            printf(" ");
        }
        printf("%s", words[i]);
        space=1;
    }
    words[index]='\0';
    return 0;
}
```
### String compression:
