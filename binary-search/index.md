# Binary Search



<!--more-->

{{< admonition type=note title="Note" open=true >}}
_Use the table of contents to navigate to the portion that you are interested in._
{{< /admonition >}}

## Introduction
We know that there is two type of searching technique `1.Linear Search` and `2.Binary Search`. Here we discus only about binary search.
***Binary search*** is a searching technique, it is used to locate a specific element with in the ***sorted array***. 
>It is applicable only on monotonic function which means values should be in the **increasing** or **decreasing** order.

## Creation of Function 
The given code snippet implements the binary search algorithm for finding a specific integer key within a sorted integer array 'arr'. It initializes 'start' and 'end' indices to the first and last elements of the array, respectively, and calculates the middle index 'mid'. Inside a while loop that continues as long as the 'start' index is less than or equal to the 'end' index, the code compares the value at index 'mid' with the given 'key'. If 'key' matches the element at 'mid', the function returns 'mid' as the index where 'key' is found. If 'key' is greater than the element at 'mid', the 'start' index is updated to 'mid + 1', effectively narrowing the search range to the right half. If 'key' is smaller, the 'end' index is updated to 'mid - 1', narrowing the search range to the left half. After each update to 'start' or 'end', 'mid' is recalculated as the average of 'start' and 'end'. If the loop concludes without finding 'key', the function returns -1 to indicate that the key is not present in the array. This binary search algorithm's efficiency lies in its ability to halve the search range with each iteration, resulting in a time complexity of O(log n), making it efficient for searching in large sorted arrays.


first initialise `start` and `end` indices to the first and last element of the array respectively. then calculate the middle index by `(start+end)/2`
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

## The Main Function
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

{{< admonition type=tip title="Fun Dose" open=false >}}
{{< youtube FMzj9UYHTPQ >}}
{{< /admonition >}}


{{< admonition type=question title="Problems" open=false >}}
{{< /admonition >}}
