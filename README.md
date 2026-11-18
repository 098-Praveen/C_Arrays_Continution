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

FREQUENCY AND DUPLICATE ELEMENTS IN ARRAYS:
FREQUENCY:  means the no of times an element appears in an array:

#include<stdio.h>
int main()
{
    int a[]={5,2,5,3,2,5,4};
    int key=5,count=0;
    int n=sizeof(a)/sizeof(a[0]);
    for(int i=0;i<n;i++)
    {
        if(a[i]==key)
        {
            count++;
        }
    }
    printf("%d",count);
}

DUPLICATING ELEMENTS:

elements that are appeared more than once.


#include<stdio.h>
int main()
{
    int i,j,n;
    int a[]={5,2,5,3,2,5,4};
    n=sizeof(a)/sizeof(a[0]);
    for(i=0;i<n;i++)
    {
        int flag=0,seen=0;
        for(j=i+1;j<n;j++)
        {
            if(a[i]==a[j])
            {
                flag=1;
            }
        }
        for(j=0;j<i;j++)
        {
            if(a[i]==a[j])
            {
                seen=1;
            }
        }
        if(flag==1&&seen==0)
        {
            printf("%d ",a[i]);
        }
    }
return 0;
}
PASSING ARRAYS TO FUNCTIONS:
IMP: when an array is passed to function, the array parameter behaves like a pointer to it's first element.
CAN FUNCTION MODIFIES THE ORIGINAL ARRAY :
 yes it does.
 #include<stdio.h>

void modify(int arr[])
{
    arr[0] = 100;
}

int main()
{
    int a[] = {10,20,30};

modify(a);

printf("%d", a[0]);

return 0;
}

PASSING ARRAY SIZE TO A FUNCTION:
IMP: A function receiving an array does not automatically know how many elements it contains.
Your first program exercise
Write a C program that:
1. Creates an array {10, 20, 30, 40, 50} inside main().
2. Passes the array and its size to a function called display().
3. The display() function prints all array elements.

#include<stdio.h>
void display(int arr[],int n)
{
    int i;
    for(i=0;i<n;i++)
    {
        printf("%d ",arr[i]);
    }
}
int main()
{
    int a[]={10,20,30,40,50};
    int n;
    n=sizeof(a)/sizeof(a[0]);
    display(a,n);
    
return 0;
}

FIND THE MAX ELEMENT:
#include<stdio.h>
int findmax(int arr[],int n)
{
    int i;
    int large=arr[0];
   for(i=0;i<n;i++)
   {
       if(large<arr[i])
       {
           large=arr[i];
       }
   }
   return large;
}
int main()
{
    int a[]={15,80,25,90,40};
    int n;
    n=sizeof(a)/sizeof(a[0]);
    int max=findmax(a,n);
    printf("max=%d ",max);
    return 0;
}

find total sum
#include<stdio.h>
int findsum(int arr[],int n)
{
    int total=0,i;
    for(i=0;i<n;i++)
    {
        total=total+arr[i];
    }
    return total;
}
int main()
{
    int a[]={10,20,30,40,50};
    int n;
    n=sizeof(a)/sizeof(a[0]);
    int sum=findsum(a,n);
    printf("sum=%d ",sum);
    return 0;
}
Next exercise: Count even numbers using a function
Write a program that:
1. Creates an array {10, 15, 20, 25, 30, 35, 40}.
2. Passes the array and its size to a function called counteven().
3. Counts the even numbers inside the function.
4. Returns the count to main().
5. Prints the count.

Your turn!

#include<stdio.h>
void eveodd(int arr[],int n,int *even,int *odd)
{
    int i;
    for(i=0;i<n;i++)
    {
        if(arr[i]%2==0)
        {
            (*even)++;
        }
        else
        {
            (*odd)++;
        }
    }
    
}
int main()
{
    int a[]={10,15,20,25,30,35,40};
    int n=sizeof(a)/sizeof(a[0]);
    int even=0,odd=0;
    eveodd(a,n,&even,&odd);
    printf("even=%d\n",even);
    printf("odd=%d",odd);
    return 0;
}

find small:
#include<stdio.h>
int findmin(int arr[],int n)
{
    int min=arr[0];
    int i;
    for(i=0;i<n;i++)
    {
        if(min>arr[i])
        {
            min=arr[i];
        }
    }
    return min;
}
int main()
{
    int a[]={45,12,78,5,32,19};
    int n=sizeof(a)/sizeof(a[0]);
    int small=findmin(a,n);
    printf("small=%d ",small);
    return 0;
}

Next Program: Search an Element Using a Function
Write a C program that:
1. Creates an array {10, 25, 30, 45, 50} inside main().
2. Passes the array, its size, and a search key to a function called search().
3. Searches for the key inside the function.
4. Returns the index if found; otherwise, returns -1.
5. Prints the result in main().
Your turn!

#include<stdio.h>
int search(int arr[],int n,int key)
{
    int found=-1;
    for(int i=0;i<n;i++)
    {
        if(arr[i]==key)
        {
            found=i;
            break;
        }
        
}
return found;
}
int main()
{
    int a[]={10,25,30,45,50};
    int n=sizeof(a)/sizeof(a[0]);
    int key=45,ret;
    ret=search(a,n,key);
    printf("%d",ret);
    return 0;
    
}
Next Program: Reverse an Array Using a Function
Write a C program that:
1. Creates an array {10, 20, 30, 40, 50} inside main().
2. Passes the array and its size to a function called reverse().
3. Reverses the original array inside the function.
4. Prints the reversed array in main().
Your turn!

#include<stdio.h>
int * reverse(int arr[],int n)
{
    int i,j,temp;
    for(i=0,j=n-1;i<=j;i++,j--)
    {
       temp=arr[i];
       arr[i]=arr[j];
       arr[j]=temp;
    }
    return arr;
}
int main()
{
    int a[]={10,20,30,40,50};
    int n=sizeof(a)/sizeof(a[0]);
    reverse(a,n);
    for(int i=0;i<n;i++)
    {
        printf("%d ",a[i]);
    }
    return 0;
}

Write a function called modify() that:
- Receives the array and its size.
- Multiplies every element by 2.
- Modifies the original array.
Print the modified array in main().

#include<stdio.h>
int modify(int arr[],int n)
{
    int i;
    for(i=0;i<n;i++)
    {
        arr[i]=arr[i]*2;
    }
}
int main()
{
    int a[]={10,20,30,40,50};
    int n=sizeof(a)/sizeof(a[0]);
    modify(a,n);
    for(int i=0;i<n;i++)
    {
        printf("%d ",a[i]);
    }
}


