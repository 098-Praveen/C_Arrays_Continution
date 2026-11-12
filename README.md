// SORTING TECHNIQUES

BUBBLE SORT:

// compare adjacent elements
#include<stdio.h>
int main()
{
    int a[]={20,10,30,50,40};
    int n=sizeof(a)/sizeof(a[0]);
    int i,j,temp;
    for(i=0;i<n-1;i++)
    {
        for(j=0;j<n-i-1;j++)
        {
            if(a[j]<a[j+1])
            {
                temp=a[j];
                a[j]=a[j+1];
                a[j+1]=temp;
            }
        }
    }
    
  for(i=0;i<n;i++)
  {
       printf("%d ",a[i]);
  }
  return 0;
}

SELECTION SORT:

first: take first element and find small or large 
second: remember it's first index
third: perform the one swap for each iteration

#include<stdio.h>
int main()
{
    int a[]={20,10,30,50,40};
    int n=sizeof(a)/sizeof(a[0]);
    int i,j,temp,key;
    for(i=0;i<n-1;i++)
    {
         key=i;
        for(j=i+1;j<n;j++)
        {
            if(a[key]<a[j])
            {
               key=j;
            }
        }
        temp=a[i];
        a[i]=a[key];
        a[key]=temp;
    }
    
  for(i=0;i<n;i++)
  {
      printf("%d ",a[i]);
  }
    return 0;
}

INSERTION SORT:
TAKE ONE ELEMENT AND COMPARE IT WITH THE NEXT ELEMENTS AND PUT IT INTO IT'S CORRECT POSITION:

#include<stdio.h>
int main()
{
    int a[]={5,2,4,1,3};
    int i,j,key,n,temp;
    n=sizeof(a)/sizeof(a[0]);
    for(i=1;i<n;i++)
    {
        key=a[i];
        j=i-1;
        while(j>=0&&a[j]<key)
        {
            a[j+1]=a[j];
            j--;
        }
        a[j+1]=key;
    }
    for(i=0;i<n;i++)
    {
        printf("%d ",a[i]);
    }
    return 0;
}
