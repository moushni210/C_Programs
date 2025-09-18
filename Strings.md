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
int astrcmp(char *str1,char *str2);
int main()
{
        char str1[30],str2[30];
        printf("enter strings: \n");
        fgets(str1,30,stdin);
        fgets(str2,30,stdin);
        if(astrcmp(str1,str2)==0)
                printf("strings are same \n");
        else
                printf("strings are not same");
        return 0;
}
int astrcmp(char *str1,char *str2)
{
        while(*str1 == *str2)
                {
                        if(*str1=='\0')
                                return 0;
                        str1++;
                        str2++;
                }
                return (*str1-*str2);
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

## 8. Write a program in C to copy one string to another string.
```c
#include<stdio.h>
int main()
{
        char str1[20],str2[20];
        printf("enter strings:\n");
        fgets(str1,20,stdin);
        fgets(str2,20,stdin);
        printf("before copy: str1: %s ,str2:%s \n",str1,str2);
        int i=0;
        while(str2[i]!='\0')
        {
                str1[i]=str2[i];
                i++;
        }
        str1[i]='\0';
        printf("after copy: str1: %s ,str2:%s \n",str1,str2);
}
```
### Output:
```
enter strings:
moushni
beauty
before copy: str1: moushni
 ,str2:beauty

after copy: str1: beauty
 ,str2:beauty
```

## 9. Write a program in C to count the total number of vowels or consonants in a string.
```c
#include<stdio.h>
#include<ctype.h>
int main()
{
        char str[30];
        printf("enter string:\n");
        fgets(str,30,stdin);
        int vowel=0,cons=0;
        for(int i=0;str[i]!='\0';i++)
        {
                if(isalpha(str[i]))
                {
                        char ch=tolower(str[i]);
                        if(ch=='a' || ch=='e' || ch=='i' || ch=='o' || ch=='u')
                                vowel++;
                        else
                                cons++;
                }
        }
        printf("vowels : %d, consonants: %d",vowel,cons);
        return 0;
}
```
### Output:
```
enter string:
Meghamala
vowels : 4, consonants: 5
```

## 10. Write a program in C to find the maximum number of characters in a string.
```c
#include<stdio.h>
int main()
{
        char str[40];
        printf("enter string:\n");
        fgets(str,40,stdin);
//      str[strcspn(str, "\n")] = '\0';
        int count=0,lar=0;
        char ch;
        for(int i=0;str[i]!='\0';i++)
        {
                count=0;
                for(int j=0;str[j]!='\0';j++)
                {
                        if(str[i]==str[j])
                                count++;
                }
                if(count>lar)
                {
                        lar=count;
                        ch=str[i];
                }
        }
        printf("maximum occurred  charcter is %c for %d times",ch,lar);
        return 0;
}
```
### Output:
```
enter string:
intellectual
maximum occurred  charcter is l for 3 times
```
```
enter string:
intellectual and intelligent
maximum occurred  charcter is l for 5 times
```

## 11.Write a program in C to read a string from the keyboard and sort it using bubble sort. 
```c
#include<stdio.h>
#include<string.h>
int main()
{
        char str[30],temp;
        printf("enter string:\n");
        fgets(str,30,stdin);
        int i,j,len=strlen(str);
        for(i=0;i<len-1;i++)
        {
                for(j=0;j<len-i-1;j++)
                {
                        if(str[j]>str[j+1])
                        {
                                temp=str[j];
                                str[j]=str[j+1];
                                str[j+1]=temp;
                        }
                }
        }
        printf("sorted string is %s",str);
        return 0;
}
```
### Output:
```enter string:
programming in c
sorted string is
  acggiimmnnoprr
```
```
enter string:
intelligent
sorted string is
eegiillnntt
```

## 12.Write a C program to sort a string array in ascending order.
```c
#include<stdio.h>
#include<string.h>
int main()
{
        char str[10][50],temp[50];
        int n,i,j;
        printf("enter n no. of strings: ");
        scanf("%d",&n);
        getchar();
        printf("enter strings:\n");
        for(int i=0;i<n;i++)
        {
                fgets(str[i],50,stdin);
                str[i][strcspn(str[i], "\n")] = '\0';
        }
        for(i=0;i< n-1;i++)
        {
                for(j=0;j< n-i-1;j++)
                {
                        if(strcmp(str[j],str[j+1])>0)
                        {
                                strcpy(temp,str[j]);
                                strcpy(str[j],str[j+1]);
                                strcpy(str[j+1],temp);
                        }
                }
        }
        printf("\nstrings in ascending order:");
        for(i=0;i<n;i++)
                printf("%s\n",str[i]);
        return 0;
}
```
### Output:
```
enter n no. of strings: 5
enter strings:
mango
papaya
apple
banana
cherry

strings in ascending order:apple
banana
cherry
mango
papaya
```

## 13. Write a program in C to extract a substring from a given string.
```c
#include<stdio.h>
#include<string.h>
int main()
{
        char str[100];
        printf("enter string:");
        fgets(str,100,stdin);
        char str1[20];
        int start,len;
        printf("enter start index and length of sub string: ");
        scanf("%d%d",&start,&len );
        strncpy(str1,str+start,len);
        str1[len]='\0';
        printf("Original string: %s\nextracted string: %s\n",str,str1);

        return 0;
}
```
### Output:
```
enter string:have a nice day!
enter start index and length of sub string: 7
4
Original string: have a nice day!

extracted string: nice
```
```
enter string:have a good day!
enter start index and length of sub string: 8
4
Original string: have a good day!

extracted string: ood
```

## 15. Write a program in C to read a sentence and replace lowercase characters with uppercase and vice versa.
```c
#include<stdio.h>
int main()
{
        char str[100];
        printf("enter string: ");
        fgets(str,100,stdin);
        for(int i=0;str[i]!='\0';i++)
        {
                if(str[i]>64 && str[i]<91)
                {
                        str[i]=str[i]+32;
                }
                else if(str[i]>96 && str[i]<123)
                {
                        str[i]=str[i]-32;
                }
        }
        printf("after changing string is: %s",str);
        return 0;
}
```
### Output:
```
enter string: BCG Strategy Consulting Job Simulation on Forage
after changing string is: bcg sTRATEGY cONSULTING jOB sIMULATION ON fORAGE
```
```
enter string: Hello everyone! I'm happy for u.
after changing string is: hELLO EVERYONE! i'M HAPPY FOR U.
```

## 17. Write a program in C to remove characters from a string except alphabets.
```c
#include<stdio.h>
#include<ctype.h>
int main()
{
        char  str[40],str1[40];
        printf("enter string: ");
        fgets(str,40,stdin);
        int j=0;
        for(int i=0;str[i]!='\0';i++)
        {
                if((isalpha(str[i])))
                {
                                str1[j]=str[i];
                                j++;
                }
        }
        str1[j]='\0';
        printf("string after removing char except alphabets: %s",str1);
        return 0;
}
```
### Output:
```
enter string: uo309-l.aw-dp;a.w'q0
string after removing char except alphabets: uolawdpawq
```
```
enter string: oawi-[ol/o0d=['LD/O0L,, Z
string after removing char except alphabets: oawiolodLDOLZ
```

## 18. Write a program in C to find the frequency of characters.
```c
#include<stdio.h>
#include<string.h>
int main()
{
        char str[40];
        printf("enter string: ");
        fgets(str,40,stdin);
        int count;
        for(int i=0;i<(strlen(str)-1);i++)
        {
                char ch=str[i];
                count=1;
                if(str[i]!=1)
                {
                        for(int j=i+1;j<(strlen(str)-1);j++)                        {
                                if(str[i]==str[j])
                                {
                                        count++;
                                        str[j]=1;
                                }
                        }
                        printf("the frequency of \'%c\' is %d\n",ch,count);
                }
        }
        return 0;
}
```
### Output:
```
enter string: hello
the frequency of 'h' is 1
the frequency of 'e' is 1
the frequency of 'l' is 2
the frequency of 'o' is 1
```
```
enter string: fantastic
the frequency of 'f' is 1
the frequency of 'a' is 2
the frequency of 'n' is 1
the frequency of 't' is 2
the frequency of 's' is 1
the frequency of 'i' is 1
the frequency of 'c' is 1
```

## 19. Write a program in C to combine two strings manually.
```c
#include<stdio.h>
int main()
{
        char str1[40],str2[30];
        printf("enter strings: ");
        gets(str1,40,stdin);
        gets(str2,30,stdin);
        int i=0,j;
        while(str1[i]!='\0')
        {

                i++;
        }
        for(j=0;str2[j]!='\0';j++)
        {
                *(str1+i+j) = str2[j];
        }
        *(str1+i+j) ='\0';
        printf("after combining str1: %s\nstr2:%s\n",str1,str2);
        return 0;
}
```
### Output:
```
enter strings: para
llel
after combining str1: parallel
str2:llel
```
