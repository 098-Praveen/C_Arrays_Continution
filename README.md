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

STAGE 13:
INSERTION AND DELETION IN ARRAYS:
for insertion an element in particual position:
FROM RIGHT TO LEFT:
#include<stdio.h>
int main()
{
    int a[6]={10,20,30,40,50};
    int i,pos=2,value=25,n;
    n=sizeof(a)/sizeof(a[0]);
    printf("n=%d\n",n);
    for(i=n-2;i>=pos;i--)
    {
        a[i+1]=a[i];
    }
    a[pos]=value;
    for(i=0;i<n;i++)
    {
        printf("%d ",a[i]);
    }
    return 0;
}

bcz index 5 is empty we need to put index 4 to 5 which is 6th position
INSERT AT LAST POSITION:
#include<stdio.h>
int main()
{
    int a[6]={10,20,30,40,50};
    int i,value=60,n;
    n=sizeof(a)/sizeof(a[0]);
   
   for(i=0;i<n-1;i++)
    {
       printf("%d ",a[i]);
    }
    printf("\n");
    a[i]=value;
    for(i=0;i<n;i++)
    {
        printf("%d ",a[i]);
    }
    return 0;
}
ARRAY DELETION:

DELETION MEANS REMOVING AN ELEMENT FROM A PARTICULAR POSITION IN AN ARRAY:
#include<stdio.h>
int main()
{
   int a[]={10,20,30,40,50};
   int pos=2,i;
   int n=sizeof(a)/sizeof(a[0]);
   for(i=pos;i<n-1;i++)
   {
       a[i]=a[i+1];
   }
   for(i=0;i<n-1;i++)
   {
       printf("%d ",a[i]);
   }
   return 0;
}
from left to right

