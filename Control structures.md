## 1.Write a c program to accept two integers and check whether they are equal or not?
```c
#include<stdio.h>
int main()
{
        int a,b;
        printf("Enter two input values:\n");
        scanf("%d %d",&a,&b);
        if(a==b)
                printf("Equal");
        else
                printf("Not Equal");
return 0;
}
```
### Output:
```
Enter two input values: 
5
7
Not Equal
``` ```
Enter two input values: 
8
8
Equal
```
## 2.Write a c program to check whether a given number is even or odd?
```c
#include<stdio.h>
int main()
{
        int a;
        scanf("%d",&a);
        if(a%2)
                printf("Odd");
        else
                printf("Even");
return 0;
}
```
### Output:
```
6
Even
``` ```
9
Odd
```
## 3.Write a c program to check whether a given number is positive or negative?
```c
#include<stdio.h>
int main()
{
        int a;
        scanf("%d",&a);
        if(a>0)
                printf("Positive");
        else
                printf("Negative");
}
```
## 4.Write a c program to find whether a given year is a leap year or not?
```c
#include<stdio.h>
int main()
{
        int a;
        scanf("%d",&a);
        if((a%400==0)||((a%4==0)&&(a%100!=0)))
                printf("Leap Year");
        else
                printf("Not a Leap Year");
return 0;
}
```
## 5.Write a c program to read the age of a candidate and determine whether he is eligible to cast his/her own vote?
```c
#include<stdio.h>
int main()
{
        int age;
        scanf("%d",&age);
        if(age>=18)
                printf("Elegible to vote");
        else
                printf("Inelegible");
return 0;
}
```
## 6.Write a c program to read the value of an integer m and display the value of n is 1 when m is larger than 0, 0 when m is 0 and -1 when m is less than 0.
```c
#include<stdio.h>
int main()
{
        int m;
        scanf("%d",&m);
        if(m>0)
                printf("N is 1");
        else if(m==0)
                printf("N is 0");
        else
                printf("N is -1");
return 0;
}
```     
## 7.Write a c program to find the largest of three numbers.
```c
#include<stdio.h>
int main()
{
        int a,b,c;
        scanf("%d %d %d",&a,&b,&c);
        if(a>b)
                if(a>c)
                        printf("a is largest");
                else
                        printf("c is largest");
        else
                if(b>c)
                        printf("b is largest");
                else
                        printf("c is largest");
return 0;
}
```    
## 8.Write a c program to check whether a character is a vowel or consonant.
```c
#include<stdio.h>
int main()
{
        char ch;
        scanf("%c",&ch);
        if( ch=='a' || ch=='e' ||ch=='i' ||ch=='o' ||ch=='u' ||ch=='A'||ch=='E' ||ch=='I' ||ch=='O' ||ch=='U')
                printf("it is a vowel");
        else
                printf("its a consonant");
return 0;
}
```
## 9.Write a c program to check whether a character is an alphabet or not.
```c
#include<stdio.h>
int main()
{
        char ch;
        scanf("%c",&ch);
        if((ch>='a' && ch<='z') || (ch>='A' && ch<='Z'))
                printf("it is an alphabet");
        else
                printf("it is not an alphabet");
return 0;
}
```
## 10.Write a c program to find minimum or maximum between two numbers.
```c
int main()
{
        int a,b;
        scanf("%d %d",&a,&b);
        if(a>b)
                printf("Max:%d",a);
        else
                printf("Max:%d",b);

        if(a<b)
                printf("Min: %d",a);
        else
                printf("Min: %d",b);
return 0;
}
```
## 11.Write a C program to print the day of the week for a given week number using switch case.
```c
#include<stdio.h>
int main()
{
        int x;
        printf("enter the week number:");
        scanf("%d",&x);
        switch(x)
        {
                case 1: printf("Sunday");
                        break;
                case 2: printf("Monday");
                        break;
                case 3: printf("Tuesday");
                        break;
                case 4: printf("Wednesday");
                        break;
                case 5: printf("Thursday");
                        break;
                case 6: printf("Friday");
                        break;
                case 7: printf("Saturday");
                        break;
                default: printf("Invalid week number");
                         break;
        }
return 0;
}
```
## 12.Write a C program to check whether a character is uppercase or lowercase.
```c
#include<stdio.h>
int main()
{
        char ch;
        printf("Enter a character");
        scanf("%c",&ch);
        if(ch>=65 && ch<=90)
                printf("Uppercase");
        else if(ch>=97 && ch<=122)
                printf("Lowercase");
        else
                printf("enter a char");
return 0;
}
```
## 13.Write a program to find number of days in month.
```c
#include<stdio.h>
int main()
{
        int x,y;
        printf("Enter Month:\n");
        scanf("%d",&x);
        switch(x){
                case 1:
                case 3:
                case 5:
                case 7:
                case 8:
                case 10:
                case 12: printf("31 days");
                case 4:
                case 6:
                case 9:
                case 11:printf("30 days");
                        break;
                case 2: printf("enter year:");
                        scanf("%d",&y);
                        if(y%400==0 || y%4==0 && y%100!=0)
                                printf("29 days");
                        else
                                printf("28 days");
                        break;
                default: printf("invalid month");
                         break;
        }
return 0;
}
```
## 14.Write a program to find maximum between two numbers using switch case.
```c
#include<stdio.h>
int main()
{
        int n1,n2,x;
        printf("Enter 2 numbers:");
        scanf("%d %d",&n1,&n2);
        x=(n1>n2)?1:2;
        switch(x){
                case 1:printf("maximum is n1:%d",n1);
                       break;
                case 2:if(n1<n2)
                               printf("maximum is n2:%d",n2);
                       break;
                default:printf("equal");
                        break;
        }
return 0;
}
```
## 15.Write a C program to print even numbers from 1 to 20 using for loop.
```c
#include<stdio.h>
int main()
{
        int i;
        printf("Even numbers:");
        for(i=1;i<20;i++){
            if(i%2==0)
                 printf("%d\n",i);
        }
return 0;
}
```
## 16.Write a C program to calculate the sum of first 100 natural numbers using a while loop.
```c
#include<stdio.h>
int main()
{
        int i=1,sum=0;
        while(i<=100)
        {
                sum=sum+i;
                i++;
        }
        printf("%d",sum);
return 0;
}
```
## 17.Write a C program to calculate the factorial of a number using a for loop.
```c
#include<stdio.h>
int main()
{
        int x,fact=1,i;
        scanf("%d",&x);
        if(x==0)
        {
        }
        else
        {
                for(i=1;i<=x;++i)
                {
                        fact=fact*i;
                }
        }       printf("factorial=%d",fact);
return 0;
}
```
## 18.Write a C program to check whether a number is prime using while loop.
```c
#include<stdio.h>
int main()
{
        int x,count=0,i=1;
        scanf("%d",&x);
        while(i<=x/2)
        {
                if(x%i==0){
                        count++;
                }
                i++;
        }
        if(count>1)
                printf("not a prime");
        else
        {
                printf("prime");
        }
return 0;
}
```
## 19.Write a C program to calculate the sum of digits of a number using while loop.
```c
#include<stdio.h>
int main()
{
        int num,r,sum=0;
        scanf("%d",&num);
        while(num)
        {
                r=num%10;
                sum=sum+r;
                num=num/10;
        }
        printf("sum=%d",sum);
return 0;
}
```
## 20.Write a C program to print the Fibonacci series up to n terms using for loop.
```c
#include<stdio.h>
int main()
{
        int i,fab,a,b,n;
        a=0;b=1;
        scanf("%d",&n);
        printf("%d %d ",a,b);
        for(i=1;i<=n-1;i++)
        {
                fab=a+b;
                a=b;
                b=fab;
                printf("%d ",fab);
        }
        printf("\n");
        return 0; 
}
```
## 21.Write a C program to reverse a number using a while loop.
```c
#include<stdio.h>
int main()
{
        int rev=0,num,n=1,r;
        scanf("%d",&num);
        while(num)
        {
                r=num%10;
                rev=(rev*10)+r;
                num=num/10;
        }
        printf("Reversed number = %d\n", rev);
    return 0;
}
```
## 22.Write a C program to find the largest element in an array using a for loop.
```c
#include <stdio.h>
int main()
{
        int arr[ ]={9,4,54,21,6};
        int i,lar=arr[0];
        for(i=1;i<5;i++){
               if(arr[i]>lar)
                {
                        lar=arr[i];
                }
        }
        printf("Largest element = %d\n", lar);
    return 0;
}
```
## 23.Write a C program to find the smallest element in an array using a for loop.
```c
#include <stdio.h>
int main()
{
        int arr[6]={9,34,6,8,19,12};
        int i=1,small;
        small=arr[0];
        while(i<6)
        {
                if(arr[i]<small)
                        small=arr[i];
                i++;
        }
        printf("Smallest element = %d\n", small);
    return 0;
}
```
## 24.Write a C program to print all elements of an array using a for loop.
```c
#include <stdio.h>
int main()
{
        int arr[]={1,2,3,3,4,5,8,9};
        int i;
        for(i=0;i<8;i++)
        {
                printf("%d\t",arr[i]);
        }
        printf("\n");
    return 0;
}
```
## 25.Write a C program to calculate the sum of elements in an array using while loop.
```c
#include<stdio.h>
int main()
{
        int arr[8],i,sum=0,n=0;
        printf("Enter array elemnts\n");
        for(i=0;i<8;i++)
        {
                scanf("%d",&arr[i]);
        }
        while(n<8)
        {
                sum=sum+arr[n];
                n++;
        }
        printf("sum of array elements: %d\n",sum);
        return 0;
}
```
## 26.Write a C program to count the number of vowels in a string using for loop.
```c
#include <stdio.h>
int main()
{
        char str[]= "hello everyone";
        int i,count=0,j;
        char strv[]="aeiouAEIOU";
        for(i=0;i<14;i++)
        {
                for(j=0;j<10;j++)
                {
                        if(str[i]==strv[j])
                         count++;
                }
        }
         printf("Number of vowels = %d\n", count);
    return 0;
}
```
## 27.Write a C program to count the number of words in a string using a while loop.
```c
#include<stdio.h>
int main()
{
        char str[100];
        int count=0,i=0;
        printf("ENTER A string:\n");
        fgets(str,sizeof(str),stdin);
        while(str[i]!= '\0')
        {
                if(str[i]== ' ' || str[i]=='\n' || str[i] =='\t')
                        count++;
                i++;
        }
        printf("No. of words=%d\n",count+1);
        return 0;
}
```
## 28.Write a c program to check whether a given string is a palindrome or not using a for loop.
```c
#include<stdio.h>
int main()
{
        char str[20];
        printf("String: ");
        scanf("%s",str);
        int i=0,len=0,j,count=0;
        while(str[len])
        {
                len++;
        }
        for(i=0,j=len-1;i<j;i++,j--) {
                if(str[i] == str[j]) {
                        count++;
                }
        }
        if(count==(len/2))
                printf("Palindrome string\n");
        else
                printf("Not a Plaindrome\n");
        return 0;
}
```
### Output:
```
String: madam
Palindrome string
``` ```
String: maester
Not a Plaindrome
```
## 29.Write a c program to concatenate two strings without using library functions using a while loop.
```c
#include<stdio.h>
int main()
{
        char str1[40],str2[40];
        printf("Enter strings: ");
        scanf("%s",str1);
        scanf("%s",str2);
        int i=0,j=0;
        while(str1[i])
        {
                i++;
        }
        while(str2[j])
        {
                str1[i+j]=str2[j];
                j++;
        }
        str1[i+j]='\0';
        printf("Strings are %s\n%s\n",str1,str2);
        return 0;
}
```
### Output:
```
Enter strings: Hello
World!
Strings are HelloWorld!
World!
```
## 30.Write a c program to find the length of a string using a for loop.
```c
#include<stdio.h>
int main()
{
        char str[20];
        printf("String: ");
        scanf("%s",str);
        int len=0;
        while(str[len])
        {
                len++;
        }
        printf("String length is %d",len);
        return 0;
}
```
### Output:
```
String: beautiful
String length is 9
```
## 31.Write a C program to covert a string to UPPERCASE using a while loop
```c
#include<stdio.h>
int main()
{
        char str[20];
        int i=0;
        scanf("%s",str);
        while(str[i]!='\0')
        {
                if(str[i]>=97 && str[i]<=122 )
                {
                        str[i]=str[i]-32;

                }
                i++;
        }
        printf("string output is : %s",str);
return 0;
}
```
## 32.Write a c program to find the power of a number using a for loop
#include<stdio.h>
int main()
{
        int base,exp,power=1,i;
        printf("Enter base and exponent:");
        scanf("%d %d",&base, &exp);
        for(i=0;i<exp;i++)
        {
                power=base*power;
        }
        printf("Power of given number is: %d",power);
        return 0;
}
## 33.WRITE A C PROGRAM TO FIND THE FACTORIAL OF A NUMBER USING A WHILE LOOP? 
```c
#include<stdio.h>
int main()
{
        int fact=1,i=1,n;
        printf("enter a number:");
        scanf("%d",&n);
        while(i<=n)
        {
                fact=fact*i;
                i++;
        }
        printf("Factorial= %d",fact);
        return 0;   
}
```
## 34.Write a c program to find the gcd of two numbers using a while loop.
```c
#include<stdio.h>
int main()
{
        int a,b,r;
        printf("Enter 2 numbers:\n");
        scanf("%d %d",&a,&b);
        while(b)
        {
                r=a%b;
                a=b;
                b=r;
        }
        printf("Gcd of 2 numbers is %d",a);
        return 0;
}
```
## 35.Write a c program to find the lcm of two numbers using a for loop.
```c
#include<stdio.h>
int main()
{
         int a,b,i;
         scanf("%d %d",&a,&b);
         for(i=1;i<(a*b);i++)
         {
                 if(((a*i)%b)==0)
                 {
                         printf("lcm is %d",(a*i));
                         break;
                 }
}
return 0;
}
```
## 36.Write a c program to print the multiplication table of a given number using a FOR loop.
```c
#include<stdio.h>
int main()
{
        int n,i;
        scanf("%d",&n);
        printf("multiplication table of %d is\n",n);
        for(i=1;i<=10;i++)
        {
                printf("%d * %d =%d \n",n,i,n*i);
        }
return 0;
}
```
## 37.Write a program in c to print the armstrong numbers between 1 and 1000 using a for loop.
```c
#include<stdio.h>
#include<math.h>
int main()
{
        int num,n,res,d,i;
        for(i=1;i<=1000;i++)
        {
                num=i;
                d=0;
                res=0;
                while(num)
                {
                        num=num/10;
                        d++;
                }
                num=i;
                while(num)
                {
                        n=num%10;
                        res+=pow(n,d);
                        num=num/10;
                }

                if(i==res)
                {
                        printf("%d is Armstrong number\n",i);
                }
        }
return 0;
}
```
## 38.Write a program in c to implement a simple calculator using switch-case statements.
```c
#include<stdio.h>
int main()
{
        int a,b,res;
        char opt;
        printf("enter values");
        scanf("%d %d",&a,&b);
        printf("choose operation");
        scanf(" %c",&opt);
        switch(opt)
        {
                case '+': res=a+b;
                          break;
                case '-': res=a-b;
                          break;
                case '/': if(b!=0)
                                  res=a/b;
                          else
                                  printf("can't be divided by 0");
                          break;
                case '*': res=a*b;
                          break;
                case '%': if(b!=0)
                                  res=a%b;
                          else
 printf("can't be divided by 0");
                          break;
                default: printf("Invalid input");
        }
        printf("result is %d\n",res);
return 0;
}
```
## 39.Write a program in c to check whether a given number is a palindrome or not using while loops and if-else statements.
```c
#include<stdio.h>
int main()
{
        int num,res=0,n,org;
        printf("enter a number\n");
        scanf("%d",&num);
        org=num;
        while(num !=0)
        {
                n=num%10;
                res=(res*10)+n;
                num=num/10;
        }
        if(org==res)
                printf("Palindrome");
else
                printf("not a palindrome");
        return 0;
}
```
## 40.Write a program in c to find the sum of elements in the lower triangular matrix using loops and if-else statements.
```c
#include<stdio.h>
int main()
{
        int i,j,m,sum=0;
        printf("Enter m*m- dimensional m value:\n");
        scanf("%d",&m);

        int mat[m][m];
        printf("enter matrix values:\n");
        for(i=0;i<m;i++){
                for(j=0;j<m;j++){
                        scanf("%d",&mat[i][j]);
                }
        }

        printf("the matrix is: \n");
         for(i=0;i<m;i++){
                for(j=0;j<m;j++){
                        printf("%d ",mat[i][j]);
                }
                printf("\n");
         }
for(i=0;i<m;i++){
                for(j=0;j<m;j++){
                        if(i>=j)
                        {
                                sum=sum+mat[i][j];
                        }
                }
        }

        printf("the sum of lower triangular matrix is: %d \n",sum);
        return 0; 
}
```
## 41.Write a program in c to find the sum of elements in the upper triangular matrix using loops and if-else statements.
```c
#include<stdio.h>
int main()
{
        int i,j,m,sum=0;
        printf("Enter m*m- dimensional m value:\n");
        scanf("%d",&m);

        int mat[m][m];
        printf("enter matrix values:\n");
        for(i=0;i<m;i++){
for(j=0;j<m;j++){
                        scanf("%d",&mat[i][j]);
                }
        }

        printf("the matrix is: \n");
         for(i=0;i<m;i++){
                for(j=0;j<m;j++){
                        printf("%d ",mat[i][j]);
                }
                printf("\n");
         }

        for(i=0;i<m;i++){
                for(j=0;j<m;j++){
                        if(i<=j)
                        {
                                sum=sum+mat[i][j];
}
 }
                        }
         printf("the sum of upper triangular matrix is: %d \n",sum);
         return 0;
  }
```
## 42.Write a program in c to remove duplicate elements from an array using loops and if-else statements.
```c
#include<stdio.h>
int main()
{
        int n,i,j,k;
        printf("Array size:");
        scanf("%d",&n);
        int arr[n];

        printf("Enter Array elements:\n");
        for(i=0;i<n;i++){
                scanf("%d",&arr[i]);
        }
        for(i=0;i<n;i++){
                for(j=(i+1);j<n;j++){
                        if(arr[i]==arr[j])
                        {
                                for(k=j;k<n-1;k++)
                                {
                                        arr[k]=arr[k+1];

                                }
                                n--;
                        }
                }
        }
        printf("Resulting Array:\n");
        for(i=0;i<n;i++){
                printf("%d ",arr[i]);
        }
return 0;
}
```

