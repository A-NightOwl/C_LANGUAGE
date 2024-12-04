Jack cheng在书上遇到一道编程题，可他不会做，没办法，他只好向你求助。题目要求判断给出的一个数是否为“真素数”。真素数的定义为：自身为素数，且自身各位数之和仍为素数。例如，11为素数，1+1=2也为素数，所以11为真素数。

**输入格式:**  
输入在一行中给出需要判断的数n.

**输出格式:**  
如果n为真素数，则输出“yes”，否则输出“no”。

**输入样例:**  
11   
**输出样例:**  
yes


---
```c
#define _CRT_SECURE_NO_WARNINGS 1
#include <stdio.h>
#include <stdlib.h>
int main()
{
    int n,i,j,k,sum=0;
    scanf("%d",&n);
    for (j = 2; j <= n / j; ++j)
    {
        if (n % j == 0)
        {
            printf("no");
            return 0;
        }

    }
    while(n>0)
    {
        k=n%10;
        n=n/10;
        sum=sum+k;
    }
    for (j = 2; j <= n / j; ++j)
    {
        if (sum % j == 0)
        {
            printf("no");
            return 0;
        }

    }
    printf("yes");
    return 0;
}
```