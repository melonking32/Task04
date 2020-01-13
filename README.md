# Task04
用数组实现循环队列
```c
#include "stdio.h"
#include "windows.h"
int a[100]={0};
int main()
{
	int n=0,m=0;
		int high=0,low=0;
	while(true)
	{
		int k1=1; 
		while(k1!=0)
		{
			int k;
			printf("办理业务请按1,不办理按0: ");
			scanf("%d",&k); 
			printf("\n");
			if(k==1)
			{
				n++;
				printf("您当前是第%d号，前面还有%d号在等待\n\n",n,m); 
				a[low]=n;//入队列 
				//printf("%d %d\n",low,a[low]);
				if (low+1>99)
					low=low+1-100;
				else 
					low=low+1;//队列尾后移 
				m++;  
			}
			else
				k1=0;
		}
		Sleep(1000);
		if(m>0)
		{
			printf("请%d号顾客到窗口办理业务\n\n",a[high]);
		high++;
		if (high>=100)
			high-=100;
		m--;
		//printf("%d\n",high);
		}
		else 
			printf("空闲\n"); 
	}
	return 0;
 } 
 ```
