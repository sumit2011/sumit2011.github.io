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

 
## Bubble sort
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
## Insertion Sort
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

## Merge Sort
```c
// 5. Merge Sort
#include <stdio.h>
// int arr[] = {12, 6, 47, 65, 38, 24, 98, 75, 82, 13, 44, 37}; // global array Decleration 

void merge(int *arr, int s, int e){
    int mid = (s+e)/2;

    int len1 = mid - s + 1;
    int len2 = e - mid;
 
    // dynamic memory allocate
    int *first = new int[len1];
    int *second = new int[len2];

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

    //merge 2 sorted arrays
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

    delete []first;
    delete []second;
}

void mergesort(int *arr, int s, int e){

    if (s >= e)
    {
        return;
    }

    int mid = (s+e)/2;
    mergesort(arr , s , mid);

    mergesort(arr , mid+1, e);

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
    int arr[10]= {1,34,32,25,76,68,45,98,23,44};
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
