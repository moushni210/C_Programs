## 42. Write a program to write all the elements of 2-D Array into 1-D Array in row wise.
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
### Output:
```
enter array size:
3
2
enter elements:
1
2
3
4
5
6
2-d matrix:
1 2
3 4
5 6
1-d array is:
1 2 3 4 5 6 
```
## 43. Write a program to write whether a matrix is symmetric or not 
```c
#include<stdio.h>
int main()
{
        int n,i,j,count=0;
        printf("enter size: ");
        scanf("%d",&n);

        int a[n][n];
        printf("enter array elements:\n");
        for(i=0;i<n;i++)  {
                for(j=0;j<n;j++)  {
                        scanf("%d",&a[i][j]);
                }
        }
//print matrix
        for(i=0;i<n;i++)  {
                for(j=0;j<n;j++)  {
                        printf("%d ",a[i][j]);
                } printf("\n");
        }
//compare rows and cols to check symmetric
        for(i=0;i<n;i++)  {
                for(j=0;j<n;j++)  {
                        if(a[i][j]==a[j][i])
                                count++;
                }
        }
        if(count==n*n)
                printf("symmetric matrix\n");
else
                printf("not a symmetric matrix\n");
}
```
### Output:
```
enter size: 3
enter array elements:
1
2
3
4
1
2
3
1
5
1 2 3
4 1 2
3 1 5
not a symmetric matrix
```
```
enter size: 3
enter array elements:
1
2
3
2
3
4
3
4
5
1 2 3
2 3 4
3 4 5
symmetric matrix
```

## 44. Write a program to check if elements of an array are distinct or not.
```c
#include<stdio.h>
int main()
{
        int n,i,j,found=0;
        printf("enter array size: ");
        scanf("%d",&n);

        int a[n];
        printf("enter elements:\n");
        for(i=0;i<n;i++)
                scanf("%d",&a[i]);

        for(i=0;i<n;i++)  {
                for(j=i+1;j<n;j++)  {
                        if(a[i]==a[j])  {
                                found=1;
                                break;
                        }
                }
        }
        if(!found)
                printf("elements of array are Distinct\n");
        else
                printf("elements of array are not distinct\n");
return 0;
}
```
### Output:
```
enter array size: 5
enter elements:
1
2
3
4
5
elements of array are Distinct
```
```
enter array size: 6
enter elements:
1
5
3
8
4
3
elements of array are not distinct
```

## 45.Write a program to remove duplicate elements from a sorted array. 
```c
#include<stdio.h>
int main()
{
        int n,i,j;
        printf("enter array size: ");
        scanf("%d",&n);

        int a[n];
        printf("enter elements in a sorted way:\n");
        for(i=0;i<n;i++)
                scanf("%d",&a[i]);

        for(i=0;i<n;i++)  {
                if(a[i]==a[i+1])  {
                        for(j=i+1;j<n;j++)
                                a[j]=a[j+1];
                        n--;
                }
        }

        printf("array after deleting duplicates:\n");
        for(i=0;i<n;i++)
                printf("%d ",a[i]);

return 0;
}
```
### Output:
```
enter array size: 7
enter elements in a sorted way:
1
1
2
3
4

4
5
array after deleting duplicates:
1 2 3 4 5 
```

## 47. Write a recursive function to find the sum of all even numbers in an array. 
```c
#include<stdio.h>
int even_sum(int a[],int n)
{
        if(n==0)
                return 0;
        int ele=a[n-1];
        return (ele%2 == 0) ? ele + even_sum(a,n-1) : even_sum(a,n-1);
}

int main()
{
        int n,i;
        printf("enter size: ");
        scanf("%d",&n);

        int arr[n];
        printf("enter elements:\n");
        for(i=0;i<n;i++)
                scanf("%d",&arr[i]);

        printf("sum of even numbers in array is %d\n",even_sum(arr,n));
        return 0;
}
```
### Output:
```
enter size: 7
enter elements:
1
2
3
4
6
7
8
sum of even numbers in array is 20
```

## 48. Write a recursive function that finds the sum of all elements of an array by repeatedly partitioning it into two almost equal parts. 
```c
#include<stdio.h>
int partitionsum(int a[],int start,int end)
{
        if (start>end)
                return 0;
        if(start==end)
                return a[start];
        int mid=(start+end)/2;
        int firstpart=partitionsum(a,start,mid);
        int secondpart=partitionsum(a,mid+1,end);
        return firstpart+secondpart;
}

int main()
{
        int n,i,res;
        printf("enter array size: ");
        scanf("%d",&n);

        int arr[n];
        printf("enter array elements:\n");
        for(i=0;i<n;i++)
                scanf("%d",&arr[i]);

        res=partitionsum(arr,0,n-1);
        printf("sum of elements after partitioning into two equal parts is %d\n",res);
}
```
### Output:
```
enter array size: 7
enter array elements:
3
2
7
12
4
6
5
sum of elements after partitioning into two equal parts is 39
```

## 49. Write a recursive function to reverse the elements of an array..
```c
#include<stdio.h>
void reverse(int a[],int start,int end)
{
        if(start >= end)
                return;
        int temp=a[start];
        a[start] = a[end];
        a[end] = temp;

        reverse(a,start+1,end-1);
}

int main()
{
        int n,i;
        printf("enter array size: ");
        scanf("%d",&n);

        int arr[n];
        printf("enter elements:\n");
        for(i=0;i<n;i++)
                scanf("%d",&arr[i]);

        reverse(arr,0,n-1);

        printf("reversed array is :\n");
        for(i=0;i<n;i++)
                printf("%d  ",arr[i]);
        printf("\n");

        return 0;
}
```
### Output:
```
enter array size: 6
enter elements:
12
3
4
5
6
7
reversed array is :
7  6  5  4  3  12
```

## 50. Write a recursive function to find whether the elements of an array are in strict ascending order or not. 
```c
#include<stdio.h>
#include<stdbool.h>

bool isascending(int a[],int n)
{
        if(n<=1)
                return true;
        if(a[n-1]<a[n-2])
                return false;
        return isascending(a,n-1);
}

int main()
{
        int n,i;
        printf("enter array size: ");
        scanf("%d",&n);

        int arr[n];
        printf("enter elements:\n");
        for(i=0;i<n;i++)
                scanf("%d",&arr[i]);

        if(isascending(arr,n))
                printf("array is in ascending order.\n");
        else
                printf("not in ascending order.\n");

        return 0;
}
```
### Output:
```
enter array size: 8
enter elements:
1
2
3
4
5
6
7
8
array is in ascending order.
```
```
enter array size: 5
enter elements:
1
4
6
3
7
not in ascending order.
```

## 51. Write a program to find the sum of rows and columns of a 2-d array and store the sums in the same array. 
```c
#include<stdio.h>
int main()
{
        int arr[4][4];
        int i,j;
        printf("Enter ele:");
        for(i=0;i<3;i++)
        {
                for(j=0;j<3;j++)
                {
                        scanf("%d",&arr[i][j]);
                }
        }
        printf("input matrix is:\n");
        for(i=0;i<3;i++)
        {
                for(j=0;j<3;j++)
                {
                        printf("%d ",arr[i][j]);
                }
                printf("\n");
        }
        int rs=0,cs=0;
        for(i=0;i<4;i++)
        {
                rs=0;
                for(j=0;j<4;j++)
                {
                        rs=rs+arr[i][j];
                }
                arr[i][3]=rs;
        }
        for(j=0;j<4;j++)
        {
                cs=0;
                for(i=0;i<4;i++)
                {
                        cs+=arr[i][j];
                }
                arr[3][j]=cs;
        }
        printf("resultant matrix is:\n");
        for(i=0;i<4;i++)
        {
                for(j=0;j<4;j++)
                {
                        printf("%d ",arr[i][j]);
                }
                printf("\n");
        }
}
```
### Output:
```
Enter ele:1
2
3
4
5
6
7
8
9
input matrix is:
1 2 3
4 5 6
7 8 9
resultant matrix is:
1 2 3 6
4 5 6 15
7 8 9 24
12 15 18 45
```

## 53. Write a program to print Spiral Matrix. A spiral matrix is a n x n square matrix formed by placing the numbers 1, 2, 3, 4 .........n² in spiral form starting from the leftmost column and topmost row. Spiral matrices can exist for both even and odd values of n. The spiral matrices for n=3, n=4, n=7 are shown below 
```c
#include<stdio.h>
int main()
{
        int n;
        printf("enter n value: ");
        scanf("%d",&n);

        int a[n][n];
        int top=0,down=(n-1),left=0,right=(n-1),i,j;
        int k=1;
        while(top<=down && left<=right){

        for(i=left;i<=right;i++){
                a[top][i]=k;
                k++;
        }
        top++;

        for(i=top;i<=down;i++){
                a[i][right]=k;
                k++;
        }
        right--;

        for(i=right;i>=left;i--){
                a[down][i]=k;
                k++;
        }
        down--;

        for(i=down;i>=top;i--){
                a[i][left]=k;
                k++;
        }
        left++;

        }

        for(i=0;i<n;i++){
                for(j=0;j<n;j++){
                        printf("%3d",a[i][j]);
                }
                printf("\n");
        }

        return 0;
}
```
### Output:
```
enter n value: 7
  1  2  3  4  5  6  7
 24 25 26 27 28 29  8
 23 40 41 42 43 30  9
 22 39 48 49 44 31 10
 21 38 47 46 45 32 11
 20 37 36 35 34 33 12
 19 18 17 16 15 14 13
 ```
```
enter n value: 4
  1  2  3  4
 12 13 14  5
 11 16 15  6
 10  9  8  7
```

## 56. Write a program to find the kth smallest element in an array.
```c
#include<stdio.h>
int kthsmall(int n,int a[n],int k)
{
        int i,j;
        for(i=0;i<n;i++){
                for(j=i+1;j<n;j++){
                        if(a[i]>a[j])
                        {
                                int temp=a[i];
                                a[i]=a[j];
                                a[j]=temp;
                        }
                }
        }
        return a[k-1];
}

int main()
{
        int n,i;
        printf("enter size: ");
        scanf("%d",&n);

        int a[n];
        printf("enter elements: \n");
        for(i=0;i<n;i++) {
                scanf("%d",&a[i]);
        }

        int k;
        printf("enter k value: ");
        scanf("%d",&k);

        int small=kthsmall(n,a,k);
        printf("the kth smallest elemnent is %d",small);
}

Output:
enter size: 6
enter elements:
6
2
4
5
1
3
enter k value: 4
the kth smallest elemnent is 4
```

## 57. Write a program to reverse a portion of an array. 
```c
#include<stdio.h>
int main()
{
        int n;
        printf("enter size: ");
        scanf("%d",&n);

        int ar[n];
        printf("enter ele :\n");
        for(int i=0;i<n;i++){
                scanf("%d",&ar[i]);
        }

        int a,b;
        printf("enter index from where to where: ");
        scanf("%d%d",&a,&b);

        int i=a,j=b;
        while(i<j)
        {
                int temp=ar[i];
                ar[i]=ar[j];
                ar[j]=temp;
                i++;
                j--;
        }
        printf("array after modified:\n");
        for(i=0;i<n;i++)
        {
                printf("%d ",ar[i]);
        }
}
```
### Output:
```
enter size: 7
enter ele :
1
2
3
4
5
6
7
enter index from where to where: 2
5
array after modified:
1 2 6 5 4 3 7 
```

## 58. Write a program to modify the elements of an array such that the first element becomes the last element of the array and all other elements are shifted towards left. 
## 1 2 3 4 5 6 7 8 9 -> 2 3 4 5 6 7 8 9 1
```c
#include<stdio.h>
int main()
{
        int i,j,n;
        printf("enter size: ");
        scanf("%d",&n);

        int a[n];
        printf("elements: \n");
        for(i=0;i<n;i++)
                scanf("%d",&a[i]);

        //1st ele becomes last ele, all other shifted towards left
        int las=a[0];
        for(i=0;i<n;i++)  {
                a[i]=a[i+1];
        }
        a[n-1]=las;

        printf("array after modified:\n");
        for(i=0;i<n;i++){
                printf("%d ",a[i]);
        }
}
```
### Output:
```
enter size: 8
elements:
1
2
3
4
5
6
7
8
array after modified:
2 3 4 5 6 7 8 1 
```
