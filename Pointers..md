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
~~~
value of 0 th element is 10
value of 1 th element is 20
value of 2 th element is 30
~~~


