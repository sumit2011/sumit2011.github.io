# Binary Search


Navigation system works on the concept of linked list.
<!--more-->

{{< admonition type=note title="Note" open=true >}}
_Use the table of contents to navigate to the portion that you are interested in._
{{< /admonition >}}

## Introduction
We know that there is two type of searching technique `1.Linear Search` and `2.Binary Search`. Here we discus only about binary search.
***Binary search*** is a searching technique, it is used to locate a specific element with in the ***sorted array***. Binary search is applicable only on monotonic function which means values should be in the **increasing** or **decreasing** order.

```c++
#include<iostream> 
using namespace std;

int binarysearch(int arr[], int size, int key)
{
    int start =0;
    int end = size-1;

    //int mid= (start+end)/2;

    int mid= start + (end-start)/2;

    while(start <= end){
        if(arr[mid] == key){
            return mid;
        }
        //go to right part
        if(key> arr[mid]){
            start= mid +1 ;
        }

        else{
            end= mid - 1;
        }

        //mid= (start+end)/2;
        mid = start + (end-start)/2;
    }
    return -1;
}
```


```c++
int main()
{
    int even[6]= {2,4,6,8,12,18};
    int odd[5]= {3,8,11,14,16};

    int evenindex= binarysearch(even, 6, 6);
    cout<<"index of 6 is "<<evenindex << endl;

    int oddindex= binarysearch(odd, 5, 14);
    cout<<"index of 14 is "<<oddindex << endl;


    return 0;
}
```
