## 1. Write a Program to print the address of variables using the address operator.
```c
#include<stdio.h>
int main()
{
        int x;
        printf("%p ",&x);
        printf("%d",x);

}

Output:
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

Output:
size of int pointer is 8
size of char pointer is 8
size of float pointer is 8
size of double pointer is 8
```
