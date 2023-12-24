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
<!-- The given code snippet implements the binary search algorithm for finding a specific integer key within a sorted integer array 'arr'. It initializes 'start' and 'end' indices to the first and last elements of the array, respectively, and calculates the middle index 'mid'. Inside a while loop that continues as long as the 'start' index is less than or equal to the 'end' index, the code compares the value at index 'mid' with the given 'key'. If 'key' matches the element at 'mid', the function returns 'mid' as the index where 'key' is found. If 'key' is greater than the element at 'mid', the 'start' index is updated to 'mid + 1', effectively narrowing the search range to the right half. If 'key' is smaller, the 'end' index is updated to 'mid - 1', narrowing the search range to the left half. After each update to 'start' or 'end', 'mid' is recalculated as the average of 'start' and 'end'. If the loop concludes without finding 'key', the function returns -1 to indicate that the key is not present in the array. This binary search algorithm's efficiency lies in its ability to halve the search range with each iteration, resulting in a time complexity of O(log n), making it efficient for searching in large sorted arrays. -->


first initialise `start` and `end` indices to the first and last element of the array respectively. then calculate the middle index by `(start+end)/2`.
Inside the while loop, compare the value of mid with the key until the start index becomes less than or equal to the end index. if key matches with the mid element it returns the mid element. If if key is greater than the mid element the start index will updated to the mid+1.
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
        if(key> arr[mid]){  //go to right part
            start= mid +1 ;
        }
        else{
            end= mid - 1;   //go to left part
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
### Output
{{< figure src="/posts/DSA/binary search/output.png" >}}

{{< admonition type=tip title="Complete Code" open=false >}}

```c++
#include<iostream> 
//it applicable only on monotonic function values should be in inc or dec order.
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

int main(){
    int even[6]= {2,4,6,8,12,18};
    int odd[5]= {3,8,11,14,16};
    int evenindex= binarysearch(even, 6, 6);
    cout<<"index of 6 is "<<evenindex << endl;
    int oddindex= binarysearch(odd, 5, 14);
    cout<<"index of 14 is "<<oddindex << endl;
    return 0;
}  
```
{{< /admonition >}}

### Time Complexity: 
    Best Case: O(1)
    Average Case: O(log N)
    Worst Case: O(log N)

### Space Complexicity
    Space Complexicity: O(1)

## Advantages of Binary Search:
* faster than linear search
* More efficient
* Minimal memory requirement
* Easy to understand and implement
* More efficient for large dataset

## Drawbacks of Binary Search:
* The array should be sorted.
* Not suitable for unordered lists
* Inefficient for small dataset
* Not adaptive for changes
* Limited to static dataset

## Applications of Binary Search:
* Database searching
* Finding elements in a array
* Used in file system to search a specific file
* In machine learning
* In Game development



{{< admonition type=question title="Problems" open=false >}}
{{< link "https://www.codingninjas.com/studio/problems/first-and-last-position-of-an-element-in-sorted-array_1082549?interviewProblemRedirection=true" "**First and Last position of an Element in Sorted Array** (Coding Ninja)" >}}

{{< /admonition >}}

### First and Last position of an element in sorted array solution

```c++

// pair <int, int> p;
//     p.first = 5;
//     p.second = 6;


#include<iostream>
using namespace std;


int firstOccurance(int arr[], int n, int key){
    int start = 0;
    int end = n-1;
    int mid = start +(end-start)/2;
    int ans = -1;
    while(start <= end)
    {
        if (arr[mid]== key)
        {
            ans = mid;
            end = mid - 1;
        }
        else if (arr[mid] < key)
        {   // go to right part
            start = mid + 1;
        }
        else if (arr[mid] > key)
        {   // go to left part
            end = mid -1;
        }
        mid = start + (end - start)/2;
    }
    return ans;
}

int lastOccurance(int arr[], int n, int key){
    int start = 0;
    int end = n-1;
    int mid = start +(end-start)/2;
    int ans = -1;
    while(start <= end)
    {
        if (arr[mid]== key)
        {
            ans = mid;
            start = mid + 1;
        }
        else if (arr[mid] < key)
        {   // go to right part
            start = mid + 1;
        }
        else if (arr[mid] > key)
        {   // go to left part
            end = mid -1;
        }
        mid = start + (end - start)/2;
    }
    return ans;
}

pair<int , int> firstAndLastOccurance(int arr[], int n, int key){
    pair<int , int > p;
    p.first = firstOccurance(arr , n, key);
    p.second = lastOccurance(arr , n , key);
    return p;

}

int main() {
    int arr[9]={1,2,3,3,3,3,3,4,5};
    cout << " first occurace of 3 is index " << firstOccurance(arr, 9 , 3) << endl;
    cout << " last occurace of 3 is index " << lastOccurance(arr, 9 , 3) << endl;
    firstAndLastOccurance(arr, 9, 3);

}

```






{{< admonition type=tip title="Fun Dose" open=false >}}
{{< youtube FMzj9UYHTPQ >}}
{{< /admonition >}}


