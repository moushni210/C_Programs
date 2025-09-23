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

## 16. Write a program in C to find the number of times a given word 'the' appears in the given string
```c
#include<stdio.h>
#include<string.h>
#include<ctype.h>
int main()
{
        char str[100];
        printf("enter string: ");
        fgets(str,100,stdin);
        str[strcspn(str, "\n")]='\0';
        char word[10];
        int count=0,i=0,j;
        while(str[i]!='\0')
        {
                j=0;
                while(str[i] != ' ' && str[i] !='\0')
                {
                        if(isalpha(str[i])){
                        word[j++] = tolower(str[i]);
                        }
                        i++;
                }
                word[j]='\0';
                if(strcmp(word, "the") == 0)
                        count++;
                if(str[i] == ' )
                        i++;
        }
        printf("in the string \"the\" has appeared %d times.\n",count);
        return 0;
}
```
### Output:
```
enter string: The quick brown fox jumps over the lazy dog. THE dog barked.
in the string "the" has appeared 3 times.
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
``` ```
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

## 20. Write a program in C to find the largest and smallest words in a string.
```c
#include<stdio.h>
#include<string.h>
int main()
{
        char str[100];
        printf("Enter string: ");
        fgets(str,sizeof(str),stdin);
        str[strcspn(str, "\n")]='\0';
        char word[20],sword[20],lword[20];
        int i=0,k=0,j,lar=0,sma=0,count=0;
        while(str[i]!= ' ')
        {
                sword[k++] = str[i++];
        }
        sword[k]='\0';
        sma=strlen(sword);
        i=0;
        while(str[i] !='\0')
        {
                if(str[i] != ' ')
                {
                        word[j++]=str[i++];
                }
                else
                {
                        word[j]='\0';
                        count=strlen(word);
                        j=0;
                        i++;
                        if(count>lar)
                        {
                                 lar=count;
                                 strcpy(lword,word);
                        }
                        else if(count<sma)
                        {
                                 sma=count;
                                 strcpy(sword,word);
                        }
                }
        }
        printf("smallest string: %s \nlargest string: %s\n",sword,lword);
        return 0;
}
```
### Output:
```
Enter string: the engineer is on a vacation
smallest string: a
largest string: engineer
```

## 21. Write a program in C to convert a string to uppercase.
```c
#include<stdio.h>
#include<string.h>
int main()
{
        char str[30];
        printf("enter string: ");
        fgets(str,sizeof(str),stdin);
        str[strcspn(str, "\n")]='\0';

        char ch;
        int i=0;
        while(str[i])
        {
                if(str[i]>=97 && str[i]<=122)
                {
                        str[i]=str[i]-32;
                }
                i++;
        }
        printf("resultant string is : \'%s\'\n",str);
        return 0;
}
```
### Output:
```
enter string: NJkjpiN ;Ij;;
resultant string is : 'NJKJPIN ;IJ;;'
``` ```
enter string: jkOJ0F-*&*8I)(IOmcld
resultant string is : 'JKOJ0F-*&*8I)(IOMCLD'
```

## 22. Write a program in C to convert a string to lowercase.
```c
#include<stdio.h>
#include<string.h>
int main()
{
        char str[30];
        printf("Enter string: ");
        fgets(str,sizeof(str),stdin);
        str[strcspn(str, "\n")]='\0';

        char ch;
        int i=0;
        while(str[i])
        {
                if(str[i]>=65 && str[i]<=90)
                {
                        str[i]=str[i]+32;
                }
                i++;
        }
        printf("Resultant string is: \'%s\'\n ",str);
        return 0;
}
```
### Output:
```
Enter string: OJP8inkvg00M9/';
Resultant string is: 'ojp8inkvg00m9/';'
``` ```
Enter string: uhdkiUJ0MOI><*&*%&HJih
Resultant string is: 'uhdkiuj0moi><*&*%&hjih'
```

## 23. Write a program in C to check whether a character is a Hexadecimal Digit or not.
```c
#include<stdio.h>
#include<ctype.h>
int main()
{
        char ch;
        printf("Enter char: ");
        scanf("%c",&ch);
                if(isxdigit(ch))
                        printf("Is hexadigit\n");
                else
                        printf("Not a hexadigit\n");
        return 0;
}
```
### Output:
```
Enter char: H
Not a hexadigit
``` ```
Enter char: f
Is hexadigit
``` ```
Enter char: 9
Is hexadigit
```

## 24. Write a program in C to check whether a letter is uppercase or not.
```c
#include<stdio.h>
#include<ctype.h>
int main()
{
        char ch;
        printf("Enter char: ");
        scanf("%c",&ch);
                if(isupper(ch))
                        printf("In Uppercase\n");
                else
                        printf("Not in Uppercase\n");
        return 0;
}
```
### Output:
```
Enter char: j
Not in Uppercase
``` ```
Enter char: C
In Uppercase
```

## 25. Write a program in C to replace the spaces in a string with a specific character.
```c
#include<stdio.h>
#include<string.h>
int main()
{
        char str[100];
        printf("Enter string: ");
        fgets(str,sizeof(str),stdin);
        str[strcspn(str, "\n")]='\0';

        char ch;
        printf("Enter char to replace space: ");
        scanf("%c",&ch);

        int i=0;
        while(str[i])
        {
                if(str[i]== ' ')
                {
                        str[i]=ch;
                }
                i++;
        }
        printf("Resultant string: \"%s\"\n",str);
        return 0;
}
```
### Output:
```
Enter string: Once upon a time , there lived a princess.
Enter char to replace space: $
Resultant string: "Once$upon$a$time$,$there$lived$a$princess."
``` ```
Enter string: Longlong ago there was a king, who is a great ruler.
Enter char to replace space: *
Resultant string: "Longlong*ago*there*was*a*king,*who*is*a*great*ruler."
```

## 26. Write a program in C to count the number of punctuation characters present in a string.  
```c
#include<stdio.h>
#include<ctype.h>
#include<string.h>
int main()
{
        char str[100];
        printf("Enter string: ");
        fgets(str,sizeof(str),stdin);
        str[strcspn(str, "\n")]='\0';

        int count=0,i=0;
        while(str[i])
        {
                if(ispunct(str[i]))
                {
                        count++;
                }
                i++;
        }
        printf("In the string %d punctuations.\n",count);
        return 0;
}
```
### Output:
```
Enter string: Hello! guys ** (0) we are here $ to #buzz
In the string 7 punctuations.
``` ```
Enter string: mo&^t*5J)m<>/?
In the string 8 punctuations.
```

## 28. Write a program in C to check whether a letter is lowercase or not. 
```c
#include<stdio.h>
#include<ctype.h>
int main()
{
        char ch;
        printf("Enter char: ");
        scanf("%c",&ch);
                if(islower(ch))
                        printf("In lowercase\n");
                else
                        printf("Not in lowercase\n");
        return 0;
}
```
### Output:
```
Enter char: a
In lowercase
``` ```
Enter char: U
Not in lowercase
``` ```
Enter char: 9
Not in lowercase
```

## 30. Write a program in C to check whether a character is a digit or not. 
```c
#include<stdio.h>
#include<ctype.h>
int main()
{
        char ch;
        printf("Enter char: ");
        scanf("%c",&ch);
                if(isdigit(ch))
                        printf("Its digit.\n");
                else
                        printf("Not a digit.\n");
        return 0;
}
```
### Output:
```
Enter char: 2
Its digit.
``` ```
Enter char: &
Not a digit.
``` ```
Enter char: j
Not a digit.
```

## 32. Write a C program to find the repeated character in a string. 
```c
#include<stdio.h>
#include<string.h>
int main()
{
        char str[30];
        printf("Enter string: ");
        fgets(str,sizeof(str),stdin);
        str[strcspn(str, "\n")]='\0';

        int i,j;
        for(i=0;i<strlen(str);i++)
        {
                if(str[i]!='0') {
                        for(j=i+1;j<strlen(str);j++) {
                                if(str[i] == str[j])
                                {
                                        str[j]='0';
                                        printf("%c is repeated.\n",str[i]);
                                }
                        }
                }
        }
        return 0;
}
```
### Output:
```
Enter string: prerana
r is repeated.
a is repeated.
``` ```
Enter string: ambica
a is repeated.
```

## 33. Write a C program to count each character in a given string. 
```c
#include<stdio.h>
#include<string.h>
int main()
{
        char str[30];
        printf("Enter string: ");
        fgets(str,sizeof(str),stdin);
        str[strcspn(str, "\n")]='\0';

        int i,j,count;
        for(i=0;i<strlen(str);i++)
        {
                count=1;
                if(str[i]!='0') {
                        for(j=i+1;j<strlen(str);j++) {
                                if(str[i] == str[j])
                                {
                                        str[j]='0';
                                        count++;
                                }
                        }
                        printf("character: %c  || count: %d\n",str[i],count);
                }
        }
        return 0;
}
```
### Output:
```
Enter string: barbaric
character: b  || count: 2
character: a  || count: 2
character: r  || count: 2
character: i  || count: 1
character: c  || count: 1
``` ```
Enter string: pharmaceutical
character: p  || count: 1
character: h  || count: 1
character: a  || count: 3
character: r  || count: 1
character: m  || count: 1
character: c  || count: 2
character: e  || count: 1
character: u  || count: 1
character: t  || count: 1
character: i  || count: 1
character: l  || count: 1
```

## 34. Write a C program to convert vowels into uppercase characters in a string.
```c
#include<stdio.h>
#include<string.h>
#include<ctype.h>
int main()
{
        char str[40];
        printf("Enter string: ");
        fgets(str,sizeof(str),stdin);
        str[strcspn(str, "\n")]='\0';

        int i=0;
        while(str[i])
        {
                if(str[i]=='a' || str[i]=='e' || str[i]=='o' || str[i]=='i' || str[i]=='u')
                {
                        str[i]=toupper(str[i]);
                }
                i++;
        }
        printf("String is \"%s\"",str);
        return 0;
}
```
### Output:
```
Enter string: moushni
String is "mOUshnI"
```

## 38. Write a C program to reverse all the vowels present in a given string. Return the newly created string.
```c
#include<stdio.h>
#include<ctype.h>
#include<string.h>
int main()
{
        char str[30],vow[30],ch;
        printf("Enter string: ");
        fgets(str,sizeof(str),stdin);
        str[strcspn(str,"\n")]='\0';

        int i=0,j=0;
        while(str[i])
        {
                ch=tolower(str[i]);
                if(ch=='a' || ch=='e' || ch=='i' || ch=='o' || ch=='u')
                {
                        vow[j++]=str[i];
                }
                i++;
        }
        vow[j]='\0';
        i=0;
        j=strlen(vow);
        while(str[i])
        {
                ch=tolower(str[i]);            
                if(ch=='a' || ch=='e' || ch=='i' || ch=='o' || ch=='u')
                {
                             str[i]=vow[j-1];
                             j--;
                }                                 
                i++;
        }
        printf("Final string is \"%s\"",str);
        return 0;
}
```
###
```
Enter string: Peculiar
Final string is "Paciluer"
``` ```
Enter string: Beautiful
Final string is "Buiutafel"
```

## 51. Write a C program to count the total number of words in a string.
```c
#include<stdio.h>
#include<string.h>
int main()
{
        char str[100];
        printf("Enter string: ");
        fgets(str,sizeof(str),stdin);
        str[strcspn(str, "\n")]='\0';

        int i=0,word=0;
        while(str[i])
        {
                if(str[i]== ' '  || str[i+1] == '\0')
                {
                        word++;
                }
                i++;
        }
        printf("%d no. of words are present.\n",word);
}
```
### Output:
```
Enter string: Hi are u alright ,it's good to see u back.
10 no. of words are present.
```

## 52. Write a C program to find the reverse of a string.
```c
#include<stdio.h>
#include<string.h>
int main()
{
        char str[100];
        printf("Enter string: ");
        fgets(str,sizeof(str),stdin);
        str[strcspn(str, "\n")]='\0';

        int i=0,j,temp;
        int len=strlen(str);
        for(i=0,j=len-1;i<j;i++,j--)
        {
                temp=str[i];
                str[i]=str[j];
                str[j]=temp;
        }
        printf("reverse of string is %s.\n",str);
        return 0;
}
```
### Output:
```
Enter string: intelligent
reverse of string is tnegilletni.
```

## 53. Write a C program to check whether a string is palindrome or not.
```c
#include<stdio.h>
#include<string.h>
#include<ctype.h>
int main()
{
        char revstr[30],orgstr[30];
        printf("Enter string: ");
        fgets(orgstr,sizeof(orgstr),stdin);
        orgstr[strcspn(orgstr, "\n")]='\0';

        strcpy(revstr,orgstr);
        int i=0,j,temp;
        int len=strlen(orgstr);
        for(i=0;i<len;i++)
        {
                orgstr[i]=tolower(orgstr[i]);
        }

        for(i=0,j=len-1;i<j;i++,j--)
        {
                temp=revstr[i];
                revstr[i]=revstr[j];
                revstr[j]=temp;
        }
        if(strcmp(revstr,orgstr) == 0)
                printf("Palindrome string.\n");
        else
                printf("Not a palindrome.\n");
        return 0;
}
```
### Output:
```
Enter string: Intelligent
Not a palindrome.
``` ```
Enter string: reviver
Palindrome string.
```

## 54. Write a C program to reverse order of words in a given string.
```c
#include<stdio.h>
#include<string.h>

void reverse(char* begin, char* end)
{
        char temp;
        while(begin < end)
        {
                temp = *begin;
                *begin++ = *end;
                *end-- = temp;
        }
}

void reversewords(char* s)
{
        char* word_start =s;
        char* temp=s;

        while(*temp)
        {
                temp++;
                if(*temp == '\0')
                {
                        reverse(word_start,temp-1);
                }
                else if(*temp == ' ')
                {
                        reverse(word_start,temp-1);
                        word_start = temp+1;
                }
        }
        reverse(s,temp-1);
}

int main()
{
        char str[100];
        printf("Enter string: ");
        fgets(str,sizeof(str),stdin);
        str[strcspn(str, "\n")]='\0';

        char* temp=str;
        reversewords(str);
        printf("Resultant: %s.\n",str);
        return 0;
}
```
### Output:
```
Enter string: i love travelling all around the world
Resultant: world the around all travelling love i.
```

## 55. Write a C program to find the first occurrence of a character in a given string.
```c
#include<stdio.h>
#include<string.h>
int main()
{
        char str[100];
        printf("Enter string: ");
        fgets(str,sizeof(str),stdin);
        str[strcspn(str, "\n")]='\0';

        char ch;
        printf("enter char: ");
        scanf("%c",&ch);

        int i=0,flag=0;
        while(str[i])
        {
                if(str[i] == ch)
                {
                        printf("first occurrence of char \'%c\' is at %d pos.\n ",ch,i+1);
                        flag=1;
                        break;
                }
                i++;
        }
        if(flag=0)
        {
                printf("\'%c\' is not present in string.\n",ch);
        }

        return 0;
}
```
### Output:
```
Enter string: amsterdam
enter char: m
first occurrence of char 'm' is at 2 pos.
```

## 56. Write a C program to find the last occurrence of a character in a given string.
```c
#include<stdio.h>
#include<string.h>
int main()
{
        char str[100];
        printf("Enter string: ");
        fgets(str,sizeof(str),stdin);
        str[strcspn(str, "\n")]='\0';

        char ch;
        printf("enter char: ");
        scanf("%c",&ch);

        int i=strlen(str)-1,flag=0;
        while(str[i]>=0)
        {
                if(str[i] == ch)
                {
                        printf("last occurrence of char \'%c\' is at %d pos.\n ",ch,i+1);
                        flag=1;
                        break;
                }
                i--;
        }
        if(flag=0)
        {
                printf("\'%c\' is not present in string.\n",ch);
        }

        return 0;
}
```
### Output:
```
Enter string: proposterous
enter char: o
last occurrence of char 'o' is at 10 pos.
```

## 57. Write a C program to search all occurrences of a character in a given string.
```c
#include<stdio.h>
#include<string.h>
int main()
{
        char str[100];
        printf("Enter string: ");
        fgets(str,sizeof(str),stdin);
        str[strcspn(str, "\n")]='\0';

        char ch;
        printf("enter char: ");
        scanf("%c",&ch);

        int i=0,flag=0;
        printf("Occurrences of \'%c\'",ch);
        while(str[i])
        {
                if(str[i] == ch)
                {
                        printf(" at %d pos.\n ",i+1);
                        flag=1;
                }
                i++;
        }
        if(flag=0)
        {
                printf("is not present in string.\n");
        }
        return 0;
}

```
### Output:
```
Enter string: proposterous
enter char: o
Occurrences of 'o' at 3 pos.
  at 5 pos.
  at 10 pos.
```

## 62. Write a C program to remove the first occurrence of a character from a string.
```c
#include<stdio.h>
#include<string.h>
int main()
{
        char str[100];
        printf("Enter string: ");
        fgets(str,sizeof(str),stdin);
        str[strcspn(str, "\n")]='\0';

        char ch;
        printf("enter char: ");
        scanf("%c",&ch);

        int i=0,j;
        while(str[i])
        {
                if(str[i] == ch)
                {
                        for(j=i;str[j]!='\0';j++)
                        {
                                str[j]=str[j+1];
                        }
                        str[j]='\0';
                        break;
                }
                i++;
        }
        printf("Resultant:\' %s \'\n",str);
        return 0;
}
```
### Output:
```
Enter string: prepone
enter char: e
Resultant:' prpone '
```

## 63. Write a C program to remove the last occurrence of a character from a string. 
```c
#include<stdio.h>
#include<string.h>
int main()
{
        char str[100];
        printf("Enter string: ");
        fgets(str,sizeof(str),stdin);
        str[strcspn(str, "\n")]='\0';

        char ch;
        printf("enter char: ");
        scanf("%c",&ch);

        int i=strlen(str)-1,j;
        while(str[i]>=0)
        {
                if(str[i] == ch)
                {
                        for(j=i;str[j]!='\0';j++)
                        {
                                str[j]=str[j+1];
                        }
                        str[j]='\0';
                        break;
                }
                i--;
        }
        printf("Resultant:\' %s \'\n",str);
        return 0;
}
```
### Output:
```
Enter string: preoperation
enter char: r
Resultant:' preopeation '
```

## 64. Write a C program to remove all occurrences of a character from a string. 
```c
#include<stdio.h>
#include<string.h>
int main()
{
        char str[100];
        printf("Enter string: ");
        fgets(str,sizeof(str),stdin);
        str[strcspn(str, "\n")]='\0';

        char ch;
        printf("enter char: ");
        scanf("%c",&ch);

        int i=0,j;
        while(str[i])
        {
                if(str[i] == ch)
                {
                        for(j=i;str[j]!='\0';j++)
                        {
                                str[j]=str[j+1];
                        }
                        str[j]='\0';
                }
                i++;
        }
        printf("Resultant:\' %s \'\n",str);
        return 0;
}
```
### Output:
```
Enter string: banana
enter char: a
Resultant:' bnn '
```

## 65. Write a C program to remove all repeated characters from a given string.
```c
#include<stdio.h>
#include<string.h>
int main()
{
        char str[30];
        printf("Enter string: ");
        fgets(str,sizeof(str),stdin);
        str[strcspn(str, "\n")]= '\0';

        int i,j,k;
        for(i=0;str[i]!='\0';i++) {
                for(j=i+1;str[j]!='\0';j++) {
                        if(str[i]==str[j]) {
                                for(k=j;str[k]!='\0';k++){
                                        str[k]=str[k+1];
                                }
                                str[k]='\0';
                        }
                }
        }
        printf("Resultant string: \"%s\"\n",str);
        return 0;
}
```
### Output:
```
Enter string: anonymous
Resultant string: "anoymus"
```  ```
Enter string: preposterous
Resultant string: "preostu"
```

## 66. Write a C program to replace the first occurrence of a character with another in a string.
```c
#include<stdio.h>
#include<string.h>
int main()
{
        char str[30],ch,rch;
        printf("Enter string: ");
        fgets(str,sizeof(str),stdin);
        str[strcspn(str, "\n")]='\0';

        printf("Enter char to search: ");
        scanf("%c",&ch);
        printf("char to replace: ");
        scanf(" %c",&rch);

        int i=0;
        while(str[i])
        {
                if(str[i]==ch) {
                        str[i]=rch;
                        break;
                }
                i++;
        }
        printf("Resulting string: \"%s\"\n",str);
        return 0;
}
```
### Output:
```
Enter string: pencilin
Enter char to search: i
char to replace: o
Resulting string: "pencolin"
```

## 67. Write a C program to replace the last occurrence of a character with another in a string. 
```c
#include<stdio.h>
#include<string.h>
int main()
{
        char str[30],ch,rch;
        printf("Enter string: ");
        fgets(str,sizeof(str),stdin);
        str[strcspn(str, "\n")]='\0';

        printf("Enter char to search: ");
        scanf("%c",&ch);
        printf("char to replace: ");
        scanf(" %c",&rch);

        int i = strlen(str)-1;
        while(i>=0)
        {
                if(str[i]==ch) {
                        str[i]=rch;
                        break;
                }
                i--;
        }
        printf("Resulting string: \"%s\"\n",str);
        return 0;
}
```
### Output:
```
Enter string: pomogranate
Enter char to search: a
char to replace: i
Resulting string: "pomogranite"
```

## 68. Write a C program to replace all occurrences of a character with another in a string. 
```c
#include<stdio.h>
#include<string.h>
int main()
{
        char str[30],ch,rch;
        printf("Enter string: ");
        fgets(str,sizeof(str),stdin);
        str[strcspn(str, "\n")]='\0';

        printf("Enter char to search: ");
        scanf("%c",&ch);
        printf("char to replace: ");
        scanf(" %c",&rch);

        int i = 0;
        while(str[i])
        {
                if(str[i]==ch) {
                        str[i]=rch;
                }
                i++;
        }
        printf("Resulting string: \"%s\"\n",str);
        return 0;
}
```
### Output:
```
Enter string: giggling
Enter char to search: g
char to replace: z
Resulting string: "zizzlinz"
```

## 69. Write a C program to find the first occurrence of a word in a given string.
```c
#include<stdio.h>
#include<string.h>
int main()
{
        char str[100],word[20];
        printf("Enter string: ");
        fgets(str,sizeof(str),stdin);
        str[strcspn(str, "\n")]='\0';

        printf("Enter word to search: ");
        scanf("%s",word);

        char *pos = strstr(str, word);
        if(pos)
                printf("First occurence at index: %ld\n",pos-str);
        else
                printf("Word not found.\n");
        return 0;
}
```
### Output:
```
Enter string: i have to test the test paper for tmrw test .
Enter word to search: test
First occurence at index: 10
```

## 70. Write a C program to find the last occurrence of a word in a given string. 
```c
#include<stdio.h>
#include<string.h>
int main()
{
        char str[100],word[20];
        printf("Enter string: ");
        fgets(str,sizeof(str),stdin);
        str[strcspn(str, "\n")]='\0';

        printf("Enter word to search: ");
        scanf("%s",word);

        char *pos = NULL, *temp = str;
        while((temp = strstr(temp, word)) != NULL)
        {
                pos = temp;
                temp++;
        }
        if(pos)
                printf("Last occurence at index: %ld\n",pos-str);
        else
                printf("Word not found.\n");
        return 0;
}
```
### Output:
```
Enter string: i have to test the test paper for tmrw test .
Enter word to search: test
Last occurence at index: 39
```

## 71. Write a C program to search all occurrences of a word in a given string.
```c
#include<stdio.h>
#include<string.h>
int main()
{
        char str[100],word[20];
        printf("Enter string: ");
        fgets(str,sizeof(str),stdin);
        str[strcspn(str, "\n")]='\0';

        printf("Enter word to search: ");
        scanf("%s",word);

        char *pos = str;
        int found=0;
        while((pos = strstr(pos, word)) != NULL)
        {
                printf("Found at index: %ld\n",pos-str);
                pos++;
                found=1;
        }
        if(!found)
                printf("Word not found.\n");
        return 0;
}
```
### Output:
```
Enter string: i have to test the test paper for tmrw test.
Enter word to search: test
Found at index: 10
Found at index: 19
Found at index: 39
```

## 72. Write a C program to count occurrences of a word in a given string.
```c
#include<stdio.h>
#include<string.h>
int main()
{
        char str[100],word[20];
        printf("Enter string: ");
        fgets(str,sizeof(str),stdin);
        str[strcspn(str, "\n")]='\0';

        printf("Enter word to search: ");
        scanf("%s",word);

        char *pos = str;
        int found=0,count=0;
        while((pos = strstr(pos, word)) != NULL)
        {
                pos++;
                found=1;
                count++;
        }
        if(found)
                printf("word occurred %d times.\n",count);
        else
                printf("Word not found.\n");
        return 0;
}
```
### Output:
```
Enter string: i have to test the test paper for tmrw test.
Enter word to search: test
word occurred 3 times.
```

## 73. Write a C program to remove the first occurrence of a word from a string.
```c
#include <stdio.h>
#include <string.h>

int main()
{
    char str[100], word[20];
    printf("Enter the string: ");
    fgets(str, sizeof(str), stdin);
    str[strcspn(str, "\n")] = '\0';

    printf("Enter the word to remove: ");
    scanf("%s", word);

    char *pos = strstr(str, word);
    if (pos) {
        int len = strlen(word);
        memmove(pos, pos + len, strlen(pos + len) + 1);
        printf("After removing first occurrence: \"%s\"\n", str);
    } else {
        printf("Word not found.\n");
    }
    return 0;
}
```
### Output:
```
Enter the string: i have to test the test paper for tmrw's test.
Enter the word to remove: test
After removing first occurrence: "i have to  the test paper for tmrw's test."
```

## 74. Write a C program to remove the last occurrence of a word in a given string. 
```c
#include <stdio.h>
#include <string.h>
int main()
{
    char str[100], word[20];
    printf("Enter the string: ");
    fgets(str, sizeof(str), stdin);
    str[strcspn(str, "\n")] = '\0';

    printf("Enter the word to remove: ");
    scanf("%s", word);

    char *pos = NULL, *temp = str;

    while((temp = strstr(temp, word)) != NULL)
    {
            pos = temp;
            temp++;
    }

    if(pos)
    {
            int len = strlen(word);
            memmove(pos, pos + len, strlen(pos + len) + 1);
            printf("After removing last occurrence: \"%s\"\n", str);
    }
    else
            printf("Word not found.\n");

    return 0;
}
```
### Output:
```
Enter the string: i have to test the test paper for tmrw's test.
Enter the word to remove: test
After removing last occurrence: "i have to test the test paper for tmrw's ."
```

## 75. Write a C program to remove all occurrences of a word in a given string.
```c
#include <stdio.h>
#include <string.h>

int main()
{
    char str[100], word[20];
    printf("Enter the string: ");
    fgets(str, sizeof(str), stdin);
    str[strcspn(str, "\n")] = '\0';

    printf("Enter the word to remove: ");
    scanf("%s", word);

    char *pos;
    int len = strlen(word),flag=0;

    while((pos = strstr(str, word)) != NULL)
    {
            memmove(pos, pos + len, strlen(pos + len) + 1);
            flag=1;
    }
    if(flag)
            printf("After removing all occurrences: \"%s\"\n", str);
    else
            printf("Word not found.\n");

    return 0;
}
```
### Output:
```
Enter the string: i have to test the test paper for tmrw's test.
Enter the word to remove: test
After removing all occurrences: "i have to  the  paper for tmrw's ."
```
