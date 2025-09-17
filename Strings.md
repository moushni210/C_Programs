## 1. Write a program in C to input a string and print it.
```c
#include<stdio.h>
int main()
{
        char str[20];
                scanf("%s",str);
        printf("string is %s",str);
        return 0;
}
```
### Output:
```
moushni
string is moushni
```

## 2. Write a program in C to find the length of a string without using library functions.
```c
#include<stdio.h>
int main()
{
        char str[100];
        printf("enter a string:\n");
        fgets(str,100,stdin);
        int i=0,len=0;
        while(str[i]!='\0')
        {
                len++;
                str[i++];
        }
        printf("length of string is %d",len);
        return 0;
}
```
### Output:
```
enter a string:
Have a nice day , also u look beautiful.
length of string is 41
```

## 3. Write a program in C to separate individual characters from a string.
```c
#include<stdio.h>
int main()
{
        char str[100];
        printf("enter string: ");
        fgets(str,100,stdin);

        printf("Individual characters:\n");
        for (int i = 0; str[i] != '\0'; i++) {
                printf("%c\n", str[i]);
        }

        return 0;
}
```
### Output:
```
enter string: beautiful
Individual characters:
b
e
a
u
t
i
f
u
l
```

## 4. Write a program in C to print individual characters of a string in reverse order.
```c
#include<stdio.h>
int main()
{
        char str[100];
        printf("enter string: ");
        fgets(str,100,stdin);
        int i=0,len=0;
        while(str[i]!='\0')
        {
                len++;
                i++;
        }
        printf("Individual charactersin reverse order:\n");
        for (i=len-2;i>=0;i--) {
                printf("%c\n", str[i]);
        }

        return 0;
}
```
### Output:
```
enter string: beautiful
Individual charactersin reverse order:
l
u
f
i
t
u
a
e
b
```

## 5. Write a program in C to count the total number of words in a string. 
```c
#include<stdio.h>
int main()
{
        char str[100];
        printf("enter string: ");
        fgets(str,100,stdin);

        int i=0,word=0;
        while(str[i]!='\0')
        {
                if(str[i]!=' ' && (str[i+1]==' ' || str[i+1]=='\0')){
                        word++;
                }
                i++;
        }
        printf("No. of words are: %d",word);
        return 0;
}
```
### Output:
```
enter string: Have a nice day , also u look beautiful.
No. of words are: 9
```

## 6. Write a program in C to compare two strings without using string library functions.
```c
#include<stdio.h>
int len(char str[])
{
        int i=0;
        while(str[i]!='\0')
        {
                i++;
        }
        return i;
}
int main()
{
        char str1[30],str2[30];
        printf("enter strings: \n");
        fgets(str1,30,stdin);
        fgets(str2,30,stdin);
        int i=0,flag,count=0;
        int len1=len(str1);
        int len2=len(str2);
        if(len1==len2)
        {
                while(i<len1)
                {
                if(*(str1+i) == *(str2+i))
                        flag=0;
                else if(*(str1+i) > *(str2+i))
                {
                        flag=1;
                        break;
                }
                else
                {
                        flag= -1;
                        break;
                }
                i++;
                }
        if(flag==0)
                printf("strings are same \n");
        else if(flag==1)
                printf("first string greater than secong string\n");
        else
                printf("first string lesser than secong string\n");
        }                                                           else
                printf("strings are not same");
        return 0;
}
```
### Output:
```
enter strings:
manga
banga
first string greater than secong string
```
```
enter strings:
Bangalore
mangalore
first string lesser than secong string
```
```
enter strings:
manta
manta
strings are same
```
```
enter strings:
maste
master
strings are not same
```

## 7. Write a program in C to count the total number of alphabets, digits and special characters in a string.
```c
#include<stdio.h>
#include<ctype.h>
int main()
{
        int alph=0,num=0,spcl=0;
        char str[100];
        printf("enter string:\n");
        fgets(str,100,stdin);
        int i=0;
        while(str[i]!='\0')
        {
                if(isalpha(str[i]))
                        alph++;
                else if(isdigit(str[i]))
                        num++;
                else if(str[i]!='\n')
                        spcl++;
                i++;
        }
        printf("alphabets are: %d\ndigits are: %d\nspecial characters are: %d\n",alph,num,spcl);
        return 0;
}
```
### Output:
```
enter string:
M0sh@210##
alphabets are: 3
digits are: 4
special characters are: 3
```
```
enter string:
mous$586*
alphabets are: 4
digits are: 3
special characters are: 2
```





