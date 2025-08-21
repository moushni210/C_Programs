## 42. Write a program to write all the elements of 2-D Array into !-D Array in row wise.

```c
#include<stdio.h>
int main()
{
        int n,i,j,m;
        printf("enter array size:\n" );
        scanf("%d%d",&n,&m);

        int a[n][m];
        printf("enter elements:\n");
        for(i=0;i<n;i++)  {
                for(j=0;j<m;j++)  {
                        scanf("%d",&a[i][j]);
                }
        }

        printf("2-d matrix:\n");
        for(i=0;i<n;i++)  {
                for(j=0;j<m;j++)  {
                        printf("%d ",a[i][j]);
                }
                printf("\n");
        }

        int r=m*n,k=0;int b[r];
        for(i=0;i<n;i++)  {
                for(j=0;j<m;j++)  {
                        b[k++] =a[i][j];
                }
        }

        printf("1-d array is:\n");
        for(i=0;i<r;i++)  {
                printf("%d ",b[i]);
        }

        return 0;
}
```
