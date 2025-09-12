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

## 14. Program to print  elements of a 2-D array by subscripting a pointer to an array variable. 
~~~c
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
~~~
### Output:
~~~
array is:
123
456
value of 0th row, 0th col element is: 1
value of 0th row, 1th col element is: 2
value of 0th row, 2th col element is: 3
value of 1th row, 0th col element is: 4
value of 1th row, 1th col element is: 5
value of 1th row, 2th col element is: 6
~~~
## 15. Program to print  elements of a 3-D array using    pointer notation.
~~~c
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
~~~
### Output:
~~~
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
~~~
## 16. Write a  simple program for call by value.
~~~c
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
~~~
### Output:
~~~
before modifying a is 10, b is 8
after modifying a is 10, b is 8
~~~

## 17. Write a simple program for call by reference.
~~~c
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
~~~
### Output:
~~~
before modifying a is 10, b is 8
after modifying a is 11, b is 7
~~~

## 18. Program to return more than one value from a function using call by    reference.
~~~
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
~~~

### Output:
~~~
value of a is 7, b is 9
 sum is 16
 difference is -2
 product id 63
~~~

## 19. Write a program to pass a 1D array to a function.
~~~c
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
~~~
### Output:
~~~
array is:
1 2 3 4 5
inside func():
3 4 5 6 7
inside main() after func()
3 4 5 6 7
~~~

## 20. Create a function that swaps two numbers using   pointers.
~~~c
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

~~~
### Output:
~~~
value of a is 10 ,b is 21
After swapping value of a is 21 , b is 10
~~~

