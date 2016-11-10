# Quick-sort
C - program code for quick sort
#include<stdio.h>
void quicksort(int [],int,int);
void main()
{
  int a[20],n,i;
  clrscr();
  printf("Enter number of element to array");
  scanf("%d",&n);
  printf("\n Enter elements to array");
  for(i=0;i<n;i++)
  {
	scanf("%d",&a[i]);
  }
  quicksort(a,0,n-1);
  printf("\n After sorting\n");
  for(i=0;i<n;i++)
  {
	printf("\t %d",a[i]);
  }
  getch();
}
void quicksort(int a[],int first,int last)
{
  int x,t,down,up;
  x=a[first];
  if(first<last)
  {
	down=first;
	up=last;
	while(down<up)
	{
		while(a[down]<=x)
		{
		     down++;
		}
		while(a[up]>x)
		{
		     up--;
		}
		if(down<up)
		{
		     t=a[down];
		     a[down]=a[up];
		     a[up]=t;
		}
	}
	if(up<=down)
	{
		t=a[up];
		a[up]=a[first];
		a[first]=t;
		quicksort(a,first,up-1);
		quicksort(a,up+1,last);
	}
   }
}
