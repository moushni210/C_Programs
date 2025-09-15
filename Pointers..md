## 1. Write a Program to print the address of variables using the address operator.
```c
#include<stdio.h>
int main()
{
        int x;
        printf("%p ",&x);
        printf("%d",x);

}
```
### Output:
```
0x7ffe03c06114 0
```
## 2. Write a program to print size of pointer variables.
```c
#include<stdio.h>
int main()
{
        int *intp;
        printf("size of int pointer is %zu\n",sizeof(intp));
        char *chp;
        printf("size of char pointer is %zu\n",sizeof(chp));
        float *ftp;
        printf("size of float pointer is %zu\n",sizeof(ftp));
        double *dbp;
        printf("size of double pointer is %zu\n",sizeof(dbp));

}
```
### Output:
```
size of int pointer is 8
size of char pointer is 8
size of float pointer is 8
size of double pointer is 8
```
## 3. Write a program to print size of pointer variables and size of values Dereferenced by them. 
```c
#include<stdio.h>
int main()
{
        int x=4,*intp;
        char w='a',*chp;
        float y=1.7,*ftp;
        double z=2.56, *dbp;

        intp =&x;
        chp= &w;
        ftp = &y;
        dbp = &z;

        printf("size of pointer variables & size of values dereferenced by them:\n size of int pointer is %zu & size of value is %zu \n size of char pointer is %zu & size of value is %zu \n size of float pointer is %zu & size of value is %zu \n  size of double pointer is %zu & size of value is %zu \n ",sizeof(intp),sizeof(x),sizeof(chp),sizeof(w),sizeof(ftp),sizeof(y),sizeof(dbp),sizeof(z));

}
```
### Output:
```
size of pointer variables & size of values dereferenced by them:
 size of int pointer is 8 & size of value is 4
 size of char pointer is 8 & size of value is 1
 size of float pointer is 8 & size of value is 4
  size of double pointer is 8 & size of value is 8
```

## 6. Write a program to declare an integer variable a, assign it a value, then declare a pointer variable, assign it the address of a, and finally print the value of a using the pointer variable. 
```c
#include<stdio.h>
int main()
{
        int a;
        a=21;
        int *ptr;
        ptr = &a;
        printf("value of a is %d",*ptr);
}
```
### Output:
```
value of a is 21
```
## 7. Write a program to print postfix/prefix increment/decrement in a pointer variable of base type int*. 
```c
#include<stdio.h>
int main()
{
        int x=21;
        int *p;
        p=&x;
        printf("value of p: %p \n",p);
        printf("postfix increment : %p\n ",p++);
        printf("Prefix increment : %p\n",++p);
        printf("value of p: %p\n",p);
        printf("postfix decrement : %p\n ",p--);
        printf("prefix decrement : %p\n",--p);
        printf("value of p: %p",p);
return 0;
}
```
### Output:
```value of p: 0x7ffc008d320c
postfix increment : 0x7ffc008d320c
 Prefix increment : 0x7ffc008d3214
value of p: 0x7ffc008d3214
postfix decrement : 0x7ffc008d3214
 prefix decrement : 0x7ffc008d320c
value of p: 0x7ffc008d320c
```
## 8.  Write a Program to print the value and address of  elements of an array using pointers notation
```c
#include<stdio.h>
int main()
{
        int arr[]={10,20,30};
        printf("value of 1st element: %d, address : %p\n",*(arr),arr);
        printf("value of 2nd element: %d, address : %p\n",*(arr+1),(arr+1));
        printf("value of 3rd element: %d, address : %p\n",*(arr+2),(arr+2));  
  return 0;
}
```
### Output:
```
value of 1st element: 10, address : 0x7ffc6d0721ec
value of 2nd element: 20, address : 0x7ffc6d0721f0
value of 3rd element: 30, address : 0x7ffc6d0721f4
```
## 9. Write a program to print the value of array elements  using pointer and subscript notation.
```c
#include<stdio.h>
int main()
{
        int arr[]={10,20,30};
        for(int i=0;i<3;i++)
                printf("value of %d th element is %d\n",i,arr[i]);
//arr[i] or *(arr+i) or *(i+arr) or i[arr]
return 0;
}
```
### Output:
```
value of 0 th element is 10
value of 1 th element is 20
value of 2 th element is 30
```

## 14. Program to print  elements of a 2-D array by subscripting a pointer to an array variable. 
```c
#include<stdio.h>
int main()
{
        int a[2][3]={{1,2,3},{4,5,6}};
        printf("array is: \n");
        for(int i=0;i<2;i++)
        {
                for(int j=0;j<3;j++)
                        printf("%d",a[i][j]);
                printf("\n");
        }

        int (*ptr)[3]=a;
        for(int i=0;i<2;i++)
                for(int j=0;j<3;j++)
                        printf("value of %dth row, %dth col element is: %d\n",i,j,*(*(ptr+i)+j));
// *(*(ptr+i)+j)  is same as ptr[i][j]  which gives values as o/p.
// ptr+i  or ptr
return 0;
}
```
### Output:
```
array is:
123
456
value of 0th row, 0th col element is: 1
value of 0th row, 1th col element is: 2
value of 0th row, 2th col element is: 3
value of 1th row, 0th col element is: 4
value of 1th row, 1th col element is: 5
value of 1th row, 2th col element is: 6
```
## 15. Program to print  elements of a 3-D array using    pointer notation.
```c
#include<stdio.h>
int main()
{
        int a[2][3][4]={
                {
                        { 1, 2, 3, 4},
                        { 5, 6, 7, 8},
                        { 9, 10, 11, 12}
                },
                {
                        { 13, 14, 15, 16},
                        { 17, 18, 19, 20},
                        { 21, 22, 23, 24}
                }
        };

        for(int i=0;i<2;i++){
                for(int j=0;j<3;j++){
                        for(int k=0;k<4;k++){
                                printf("%d ",a[i][j][k]);
                        }printf("\n");
                }printf("\n");
        }

        for(int i=0;i<2;i++)
                for(int j=0;j<3;j++)
                        for(int k=0;k<4;k++)
                                printf("value of a[%d][%d][%d] is %d\n",i,j,k,*(*(*(a+i)+j)+k));
 return 0;
}
```
### Output:
```
1 2 3 4
5 6 7 8
9 10 11 12

13 14 15 16
17 18 19 20
21 22 23 24

value of a[0][0][0] is 1
value of a[0][0][1] is 2
value of a[0][0][2] is 3
value of a[0][0][3] is 4
value of a[0][1][0] is 5
value of a[0][1][1] is 6
value of a[0][1][2] is 7
value of a[0][1][3] is 8
value of a[0][2][0] is 9
value of a[0][2][1] is 10
value of a[0][2][2] is 11
value of a[0][2][3] is 12
value of a[1][0][0] is 13
value of a[1][0][1] is 14
value of a[1][0][2] is 15
value of a[1][0][3] is 16
value of a[1][1][0] is 17
value of a[1][1][1] is 18
value of a[1][1][2] is 19
value of a[1][1][3] is 20
value of a[1][2][0] is 21
value of a[1][2][1] is 22
value of a[1][2][2] is 23
value of a[1][2][3] is 24
```
## 16. Write a  simple program for call by value.
```c
#include<stdio.h>
int modify(int a,int b)
{
        a++;
        b--;
}

int main()
{
        int a=10,b=8;
        printf("before modifying a is %d, b is %d\n",a,b);
        modify(a,b);
        printf("after modifying a is %d, b is %d\n",a,b);
}
```
### Output:
```
before modifying a is 10, b is 8
after modifying a is 10, b is 8
```

## 17. Write a simple program for call by reference.
```c
#include<stdio.h>
int modify(int *xptr, int *yptr)
{
        (*xptr)++;
        (*yptr)--;
}

int main()
{
        int a=10,b=8;
        printf("before modifying a is %d, b is %d\n",a,b);
        modify(&a,&b);
        printf("after modifying a is %d, b is %d\n",a,b);
        return 0;
}
```
### Output:
```
before modifying a is 10, b is 8
after modifying a is 11, b is 7
```

## 18. Program to return more than one value from a function using call by    reference.
```
#include<stdio.h>
void func(int x, int y,int *ps,int *pd,int *pm)
{
        *ps=x+y;
        *pd=x-y;
        *pm=x*y;

}

int main()
{
        int a, b,sum ,diff,mul;
        a=7;b=9;
        printf("value of a is %d, b is %d\n",a,b);
        func(a,b,&sum,&diff,&mul);
        printf(" sum is %d\n difference is %d\n product id %d\n",sum,diff,mul);
        return 0;
}
```

### Output:
```
value of a is 7, b is 9
 sum is 16
 difference is -2
 product id 63
```

## 19. Write a program to pass a 1D array to a function.
```c
#include<stdio.h>
int func(int a[]);
int main()
{
        int i,arr[5]={1,2,3,4,5};
        printf("array is:\n");
        for(i=0;i<5;i++)
                printf("%d ",arr[i]);
        printf("\n");
        func(arr);
        printf("inside main() after func()\n");
        for(i=0;i<5;i++)                                                    printf("%d ",arr[i]);                               printf("\n");
        return 0;
}
int func(int a[])
{
        int i;
        printf("inside func():\n");
        for(i=0;i<5;i++)
                printf("%d ",a[i]+=2);
        printf("\n");

}
```
### Output:
```
array is:
1 2 3 4 5
inside func():
3 4 5 6 7
inside main() after func()
3 4 5 6 7
```

## 20. Create a function that swaps two numbers using   pointers.
```c
#include<stdio.h>
int swap(int *pa,int *pb)
{
        int temp;
        temp= *pa;
        *pa = *pb;
        *pb =temp;
}

int main()
{
        int a=10,b=21;
        printf("value of a is %d ,b is %d\n",a,b);
        swap(&a,&b);
        printf("After swapping value of a is %d , b is %d\n",a,b);
        return 0;
}

```
### Output:
```
value of a is 10 ,b is 21
After swapping value of a is 21 , b is 10
```
## 21. Implement a function that returns the length of a string using pointers 
```c
#include<stdio.h>
int len(char *str);
int main()
{
        char str[30];
        printf("enter string: ");
        fgets(str,30,stdin);
        int length=len(str);
        printf("length of the string is %d",length);
}
int len(char *st)
{
        int i=0;
        while(*st != '\0')
        {
                i++;
                st++;
        }
        return i;
}
```
### Output:
```
enter string: hello everyone
length of the string is 15
```
## 22. Write a program to find the maximum and minimum elements in an array using pointers.
```c
#include<stdio.h>
int larandsma(int *p,int n,int *max,int *min)
{
        int i;
        *min=*p;
        *max=*p;
        for(i=1;i<n;i++){
                if(*(p+i)<*min)
                        *min=*(p+i);
                if(*(p+i)>*max)
                        *max=*(p+i);
        }
}
int main()
{
        int arr[]={8,2,58,83,5,46,33,72,21,10};
        int min,max;
        int size = sizeof(arr) / sizeof(arr[0]);
        larandsma(arr,size,&max,&min);
        printf("largest : %d, smallest : %d\n",max,min);
        return 0;
}
```
### Output:
```
largest : 83, smallest : 2
```
## 23. Develop a function to reverse a string in place using pointers. 
```c
#include<stdio.h>
#include<string.h>
void reverse(char *st);
int main()
{
        char str[20];
        printf("enter string: ");
        fgets(str,20,stdin);
        reverse(str);
        printf("string after reverse: %s\n",str);
        return 0;
}
void reverse(char *st)
{
        int i,j;
        char temp;
        for(i=0,j=strlen(st)-1;i<j;i++,j--)
        {
                temp=*(st+i);
                *(st+i)=*(st+j);
                *(st+j)= temp;
        }
}
```
### Output:
```
enter string: moushni
string after reverse:
inhsuom
```
## 24. Write a program that calculates the sum of all elements in an integer array using pointer arithmetic.
```c
#include<stdio.h>
int main()
{
        int n,i;
        printf("enter n: ");
        scanf("%d",&n);
        int arr[n];
        for(i=0;i<n;i++)
                scanf("%d",&arr[i]);
        int sum=0;
        i=0;
        while(i<n)
        {
                sum=*(arr+i)+sum;
                i++;
        }
        printf("sum is: %d",sum);
        return 0;
}
```
### Output:
```
enter n: 6
1
2
3
4
5
6
sum is: 21
```
## 25. Implement a function to copy one string into another using pointers, without using any standard library functions 
```c
#include<stdio.h>
int main()
{
        char str1[20],str2[20];
        printf("enter string: ");
        fgets(str1,20,stdin);
        fgets(str2,20,stdin);
        printf("before copying: str1: %s str2: %s",str1,str2);
        for(int i=0;i<20;i++)
        {
                *(str1+i) = *(str2+i);
        }
        printf("after copying: str1: %s str2: %s",str1,str2);
        return 0;
}
```
### Output:
```
enter string: parrot
peacock
before copying: str1: parrot
 str2: peacock
after copying: str1: peacock
 str2: peacock
```
## 26.  Write a program to compare two strings lexicographically (like the strcmp function) using pointers.
```c
#include<stdio.h>
int main()
{
        char str1[20],str2[20];
        int flag,i=0;
        printf("enter strings:\n");
        fgets(str1,20,stdin);
        fgets(str2,20,stdin);
        while(i<20)
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
        else
                printf("strings are not same.\n");
        return 0;
}
```
### Output:
```
***o/p1:
enter strings:
priys
priya
strings are not same.

***o/p2:
enter strings:
pretty
pretty
strings are same

***o/p3:
enter strings:
manga
banga
strings are not same.
```
## 27.  Develop a function to reverse an array of integers in place using pointers. 
```c
#include<stdio.h>
int reverse(int n,int arr[n]);
int main()
{
        int n;
        printf("enter n: ");
        scanf("%d",&n);
        int arr[n];
        for(int i=0;i<n;i++)
                scanf("%d",&arr[i]);
        reverse(n,arr);
        printf("reversed array is: ");
        for(int i=0;i<n;i++)
                printf("%d ",arr[i]);
        return 0;
}
int reverse(int n,int *arr)
{
        int i,j,temp;
        for(i=0,j= n-1;i<j;i++,j--)
        {
                temp = *(arr+i);
                *(arr+i) = *(arr+j);
                *(arr+j) = temp;
        }
}
```
### Output:
```
enter n: 6
1
2
3
4
5
6
reversed array is: 6 5 4 3 2 1
```
## 28.  Write a program to find the largest element using Dynamic Memory Allocation.
```c
#include<stdio.h>
#include<stdlib.h>
int main()
{
        int *p,n,i;
        printf("enter no. of elements: ");
        scanf("%d",&n);
        p=(int *)malloc(n*sizeof(int));
        if(p==NULL)
        {
                printf("memory not avalable.\n");
                exit(1);
        }
        printf("enter elements:\n");
        for(i=0;i<n;i++)
        {
                scanf("%d",&p[i]);
        }
        int lar=p[0];
        for(i=1;i<n;i++)
        {
                if(p[i]>lar)
                {
                        lar=p[i];
                }
        }
        printf("largest element is %d",lar);
        return 0;
}
```
### Output:
```
enter no. of elements: 7
enter elements:
9
32
12
43
5
22
8
largest element is 43
```
## 29. Write a program in C to calculate the length of a string using a pointer.
```c
#include<stdio.h>
int main()
{
        char str[100];
        int len=0;char *ptr;
        printf("enter string: ");
        fgets(str,100,stdin);
        ptr=str;
        while(*ptr !='\0')
        {
                len++;
                ptr++;
        }
        printf("length of string is %d\n",len);
return 0;
}
```
### Output:
```
enter string: my name
length of string is 8
```
```
enter string: lets go fun
length of string is 12
```
```
enter string: i'm so happy
length of string is 13
```
## 30. Write a program  to swap elements using call by reference. 
```c
#include<stdio.h>
int swap(int *x,int *y);
int main()
{
        int a,b;
        printf("enter a, b values: ");
        scanf("%d%d",&a ,&b);
        swap(&a,&b);
        printf("swapped values a=%d, b=%d",a,b);
        return 0;
}
int swap(int *x,int *y)
{
        int temp=*x;
        *x = *y;
        *y = temp;
}
```
### Output:
```
enter a, b values: 21
10
swapped values a=10, b=21
```
## 31. Write a program to find the factorial of a given number using pointers. 
```c
#include<stdio.h>
void findFactorial(int num, int *fact)
{
        *fact = 1;
        for (int i = 1; i <= num; i++) {
                *fact *= i;
    }
}
int main()
{
        int n,res;
        printf("enter n value: ");
        scanf("%d",&n);
        findFactorial(n,&res);
        printf("factorial of %d is %d",n,res);
        return 0;
}
```
### Output:
```
enter n value: 6
factorial of 6 is 720
```
```
enter n value: 7
factorial of 7 is 5040
```
## 32. Write a program to count the number of vowels and consonants in a string using a pointer.
```c
#include<stdio.h>
#include<ctype.h>
int main()
{
        char str[100];
        printf("enter string: ");
        fgets(str,100,stdin);
        int vowel=0,cons=0;
        char *p;
        p = str;
        while(*p != '\0')
        {
                if(isalpha(*p))
                {
                        char ch=tolower(*p);
                        if(ch=='a' || ch=='e' || ch=='i' || ch=='o' || ch=='u')
                                vowel++;
                        else
                                cons++;
                }
                *p++;
        }
        printf("In the string, vowels: %d, consonants: %d",vowel,cons);
        return 0;
}
```
### Output:
```
enter string: My name is Moushni
In the string, vowels: 6, consonants: 9
```

## 33.  Write a program  to sort an array using a pointer
```c
#include<stdio.h>
int main()
{
        int n;
        printf("enter array size: ");
        scanf("%d",&n);
        int arr[n];
        for(int i=0;i<n;i++)
                scanf("%d",&arr[i]);
        int *p;
        p=arr;
        for(int i=0;i<n-1;i++)
        {
                for(int j=i+1;j<n;j++)
                {
                        if(*(p+j) >*(p+i))
                        {
                                int temp= *(p+i);
                                *(p+i) = *(p+j);
                                *(p+j) = temp;
                        }
                }
        }
        printf("sorted array is: ");
        for(int i=0;i<n;i++)
                printf("%d ",arr[i]);
        return 0;
}
```
### Output:
```
enter array size: 6
4
3
2
6
5
9
sorted array is: 9 6 5 4 3 2
```


## 34. Write a  program to demonstrate how a function returns a pointer.
```c
#include<stdio.h>
int* findLarger(int *a, int *b) {
    if (*a > *b)
        return a;
    else
        return b;
}

int main()
{
    int x = 10, y = 20;
    int *larger = findLarger(&x, &y);
    printf("The larger number is: %d\n", *larger);
    return 0;
}
```
### Output:
```
The larger number is: 20
```
## 35. Write a program  to compute the sum of all elements in an array using pointers 
```c
#include<stdio.h>
int main()
{
        int n,i;
        printf("enter array size: ");
        scanf("%d",&n);
        printf("enter elements:");
        int arr[n];
        for(i=0;i<n;i++)
                scanf("%d",&arr[i]);

        int sum=0,*ptr;
ptr=arr;
        for(i=0;i<n;i++)
        {
                sum=sum+(*(ptr+i));
        }
        printf("sum is %d",sum);
        return 0;

}
```
### Output:
```
enter array size: 7
enter elements:1
2
3
4
5
6
7
sum is 28
```
## 36. Write a program  to print the elements of an array in reverse order.
```c
#include<stdio.h>
int main()
{
        int n,i;
        printf("enter size : ");
        scanf("%d",&n);
        int a[n];
        printf("enter ele: ");
        for(i=0;i<n;i++)
                scanf("%d",&a[i]);
        int *ptr;
        ptr=a;
        printf("reverse order: \n");
        for(i= n-1;i>=0;i--)
                printf("%d ",*(ptr+i));
        return 0;
}
```
### Output:
```
enter size : 7
enter ele: 1
2
3
4
5
6
7
reverse order:
7 6 5 4 3 2 1
```
## 37. Write a program to show a pointer to an array whose contents are pointers to structures. 
```c
#include <stdio.h>
#include <stdlib.h>

struct Student {
    int roll;
    char name[20];
};                                                                                                                      int main() {                                                    // Create structure pointers                                struct Student *s1 = (struct Student *)malloc(sizeof(struct Student));
    struct Student *s2 = (struct Student *)malloc(sizeof(struct Student));

    // Initialize structure data
    s1->roll = 101;
    snprintf(s1->name, sizeof(s1->name), "Alice");

    s2->roll = 102;
    snprintf(s2->name, sizeof(s2->name), "Bob");

    // Array of pointers to structures
    struct Student *arr[2];
    arr[0] = s1;
    arr[1] = s2;
    
    // Pointer to the array
    struct Student **ptr = arr;

    // Accessing data using pointer to array
    for (int i = 0; i < 2; i++) {
        printf("Student %d: Roll = %d, Name = %s\n", i + 1, ptr[i]->roll, ptr[i]->name);
    }

    // Free memory
    free(s1);
    free(s2);

    return 0;
}
```
### Output:
```
Student 1: Roll = 101, Name = Alice
Student 2: Roll = 102, Name = Bob
```
