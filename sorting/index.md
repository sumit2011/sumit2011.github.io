# Sorting Algos

***Python is used in automation of taskes.***
<!--more-->

{{< admonition type=note title="Note" open=true >}}
_Use the table of contents to navigate to the portion that you are interested in._
{{< /admonition >}}

# Introduction
asdfghjklsdfghj


# Types
 1. bubble sort
 2. insertion sort
 3. merge sort
 4. quick sort
 5. selection sort
 6. heap sort
 
## Bubble sort
Bubble sort is a simple comparison-based sorting algorithm. it repeatedly compares adjacent elements and swap them if they are in the wrong order. In each iteration the largest element bubbles up to the end of the list. You can visualize it in the given page.

### Time & Space Complexity: 
| Time Complexicity |
| ------ | ----------- |
|  Best Case:  | O(n) |
|  Average Case: | O(n²) |
|  Worst Case:  | O(n²) |


| Space Complexicity |
| ------ | ----------- |
|  Best Case:  | O(1) |

### Code
```c
// 1. Bubble sort
void BubbleSort(int *arr, int length)
{
    for (int i = 0; i < length - 1; i++)
    {
        for (int j = 0; j < length - i - 1; j++)
        {
            if (arr[j] > arr[j + 1])
            {
                int temp = arr[j];
                arr[j] = arr[j + 1];
                arr[j + 1] = temp;
            }
        }
    }
}

```

{{< admonition type=note title="code in javascript" open=false >}}
```js
// javascript code
function bubbleSort(arr){
    const n = arr.length;
    for(let i = 0 ; i< n-1 ; i++ ){
        for(let j = 0 ; j< n-i-1 ; j++){
            if(arr[j] > arr[j+1]){
                let temp = arr[j];
                arr[j] = arr[j+1];
                arr[j+1] = temp;
            }
        }
    }
    return arr;
}

```
{{< /admonition >}}

{{< admonition type=success title="code in java" open=false >}}
```java
// java code
public static void bubbleSort(int[] arr){
    int n = arr.length;
    for(int i = 0 ; i< n-1 ; i++ ){
        for(int j = 0 ; j< n-i-1 ; j++){
            if(arr[j] > arr[j+1]){
                int temp = arr[j];
                arr[j] = arr[j+1];
                arr[j+1] = temp;
            }
        }
    }
}

```
{{< /admonition >}}

{{< admonition type=warning title="code in python" open=false >}}
```python
# python code
def bubbleSort(arr):
    n = len(arr)
    
    for i in range(n-1):
        for j in range(n-i-1):
            if arr[j] > arr[j+1]:
                # swap
                arr[j] , arr[j+1] = arr[j+1] , arr[j]

    return arr

```
{{< /admonition >}}

## Insertion Sort
**Insertion Sort** is a simple comparison based sorting algo. it builds the sorted list one element at a time. It works by taking each element and inserting it into its correct postion within the already sorted part of the array.

### Time & Space Complexity: 
| Time Complexicity |
| ------ | ----------- |
|  Best Case:  | O(n) |
|  Average Case: | O(n²) |
|  Worst Case:  | O(n²) |

> best case: O(n) -> when array is already sorted.

| Space Complexicity |
| ------ | ----------- |
|  Best Case:  | O(1) |

### Code
```c
// 2. Insertion sort
void InsertionSort(int *arr, int length)
{
    for (int i = 1; i < length; i++)
    {
        int value = arr[i];
        int j = i - 1;

        while (j >= 0 && arr[j] > value)
        {
            arr[j + 1] = arr[j];
            j--;
        }
        arr[j + 1] = value;
    }
}
```

{{< admonition type=success title="code in java" open=false >}}
```java
// java code
public static void insertionSort(int[] arr){
    int n = arr.length;
    for(int i = 1 ; i< n ; i++ ){
        int value = arr[i];
        int j = i-1;

        while( j>= 0 && arr[j] > value){
            arr[j+1] = arr[j];
            j--;
        }
        arr[j+1] = value;
    }
}

```
{{< /admonition >}}

{{< admonition type=note title="code in javascript" open=false >}}
```js
// javascript code
function insertionSort(arr){
    const n = arr.length;

    for(let i = 1 ; i< n ; i++ ){
        let value = arr[i];
        let j = i-1;

        while(j >= 0 && arr[j] > value){
            arr[j+1] = arr[j];
            j--;
        }
        arr[j+1] = value;
    }
    return arr;
}

```
{{< /admonition >}}



{{< admonition type=warning title="code in python" open=false >}}
```python
# python code
def insertionSort(arr):
    n = len(arr)
    
    for i in range(1, n):
        value = arr[i]
        j = i-1

        while j>= 0 and arr[j] > value:
            arr[j+1] = arr[j]
            j -= 1
        
        arr[j+1] = value

    return arr

```
{{< /admonition >}}


## Merge Sort
```c
// 5. Merge Sort
#include <stdio.h>
int arr[] = {12, 6, 47, 65, 38, 24, 98, 75, 82, 13, 44, 37}; // global array Decleration for all the sorting Algorithum



void merge(int *arr, int s, int e){
    int mid = (s+e)/2;      // finding midpoint of the array

    int len1 = mid - s + 1; //length of left part of the array
    int len2 = e - mid;     // length of right part of the array
 
    // dynamic memory allocate
    int *first = new int[len1];     // left array
    int *second = new int[len2];    // right array

    // copy values in left part
    int mainArrayIndex = s;
    for (int i = 0; i < len1; i++)
    {
        first[i] = arr[mainArrayIndex++];
    }

    // copy values in right part
    mainArrayIndex = mid + 1;
    for (int i = 0; i < len2; i++)
    {
        second[i] = arr[mainArrayIndex++];
    }

    //merging 2 sorted arrays
    int index1 = 0;
    int index2 = 0;

    mainArrayIndex = s;

    while (index1 < len1 && index2< len2)
    {
        if (first[index1] < second[index2])
        {
            arr[mainArrayIndex++] = first[index1++];
        }
        else{
            arr[mainArrayIndex++] = second[index2++];
        }
        
    }

    while (index1 < len1)
    {
        arr[mainArrayIndex++] = first[index1++];
    }

    while (index2 < len2)
    {
        arr[mainArrayIndex++] = second[index2++];
    }  
    // free the memory
    delete []first;
    delete []second;
}

void mergesort(int *arr, int s, int e){
    // base case
    if (s >= e)
    {
        return;
    }
    // mid point
    int mid = (s+e)/2;
    // sorting left part
    mergesort(arr , s , mid);
    // sorting right part
    mergesort(arr , mid+1, e);
    // merging sorted arrays
    merge(arr , s, e); 
}


// For Displaying the sorted array or unsorted also
void Display(int *arr, int length)
{
    for (int i = 0; i < length; i++)
    {
        printf("%d ", arr[i]);
    }
}

int main()
{
    // int arr[10]= {1,34,32,25,76,68,45,98,23,44};
    int n=12;
    mergesort(arr , 0 , n-1);
    Display(arr,n);
}
```
## Quick Sort
```c
// 4. Quick Sort with partition code
int partition(int *arr, int low, int high)
{
    int pivot = arr[low];
    int i = low + 1;
    int j = high;

    do
    {
        while (arr[i] <= pivot)
        {
            i++;
        }

        while (arr[j] > pivot)
        {
            j--;
        }

        if (i < j)
        {
            int temp = arr[i];
            arr[i] = arr[j];
            arr[j] = temp;
        }
    } while (i < j);

    int value = arr[low];
    arr[low] = arr[j];
    arr[j] = value;

    return j;
}

void QuickSort(int *arr, int low, int high)
{
    if (low < high)
    {
        int partitionIndex = partition(arr, low, high);
        QuickSort(arr, low, partitionIndex - 1);
        QuickSort(arr, partitionIndex + 1, high);
    }
}
```

## Selection Sort
```c
void SelectionSort(int *arr, int length)
{
    for (int i = 0; i < length; i++)
    {
        int min_index = i;
        for (int j = i + 1; j < length; j++)
        {
            if (arr[min_index] > arr[j])
            {
                min_index = j;
            }
        }
        if (min_index != i)
        {
            int temp = arr[i];
            arr[i] = arr[min_index];
            arr[min_index] = temp;
        }
    }
}
```
