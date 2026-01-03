# Sorting Algos

***Python is used in automation of taskes.***
<!--more-->

{{< admonition type=note title="Note" open=true >}}
_Use the table of contents to navigate to the portion that you are interested in._
{{< /admonition >}}

## 1. Introduction
**Sorting** is a process of arranging data in a specific order. ususally ascending or descending. It helps to find elements faster. also it organise data for better understanding.
Diff Types of sorting algorithms:
 1. bubble sort
 2. insertion sort
 3. merge sort
 4. quick sort
 5. selection sort
 6. heap sort
 

## 2. Sorting visualizer
This visualizer gives you the clear understanding of all the sorting algos. How it works internally and how the elements are being compared everything.
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />

  <style>
    body {
      font-family: Arial, sans-serif;
      /* text-align: center; */
    }

    #container {
      display: flex;
      align-items: flex-end;
      justify-content: center;
      height: 220px;
      margin-top: 20px;
      border: 2px solid #a19696ff;
    }

    .bar {
      width: 20px;
      margin: 0 2px;
      background-color: steelblue;
    }

    button, select {
      margin: 5px;
      padding: 6px 12px;
      cursor: pointer;
    }
  </style>
</head>
<body>


<!-- Controls -->
<div id="controls" style="display: flex; align-items: center; justify-content: center; gap: 10px; margin-bottom: 15px; flex-wrap: wrap;">
  <select id="algorithm" style="padding: 6px 12px; font-size: 1rem; cursor: pointer; max-width: 250px; width: 100%;">
    <option value="bubble">Bubble Sort</option>
    <option value="selection">Selection Sort</option>
    <option value="insertion">Insertion Sort</option>
    <option value="merge">Merge Sort</option>
    <option value="quick">Quick Sort</option>
  </select>

  <button onclick="generateArray()" style="padding: 6px 12px; font-size: 1rem; cursor: pointer; max-width: 250px; width: 100%;">Generate Array</button>
  <button onclick="sortArray()" style="padding: 6px 12px; font-size: 1rem; cursor: pointer; max-width: 250px; width: 100%;">Sort</button>
</div>


<div id="container"></div>

<script>
let array = [];
const container = document.getElementById("container");

function generateArray() {
  container.innerHTML = "";
  array = [];
  for (let i = 0; i < 20; i++) {
    const value = Math.floor(Math.random() * 200) + 20;
    array.push(value);

    const bar = document.createElement("div");
    bar.classList.add("bar");
    bar.style.height = value + "px";
    container.appendChild(bar);
  }
}

async function sortArray() {
  const algo = document.getElementById("algorithm").value;
  if (algo === "bubble") await bubbleSort();
  if (algo === "selection") await selectionSort();
  if (algo === "insertion") await insertionSort();
  if (algo === "merge") await mergeSort(array, 0, array.length - 1);
  if (algo === "quick") await quickSort(array, 0, array.length - 1);
}

function sleep(ms) {
  return new Promise(resolve => setTimeout(resolve, ms));
}

// Bubble Sort
async function bubbleSort() {
  const bars = document.getElementsByClassName("bar");
  for (let i = 0; i < array.length - 1; i++) {
    for (let j = 0; j < array.length - i - 1; j++) {
      bars[j].style.backgroundColor = "red";
      bars[j+1].style.backgroundColor = "red";

      if (array[j] > array[j+1]) {
        [array[j], array[j+1]] = [array[j+1], array[j]];
        bars[j].style.height = array[j] + "px";
        bars[j+1].style.height = array[j+1] + "px";
      }

      await sleep(100);

      bars[j].style.backgroundColor = "steelblue";
      bars[j+1].style.backgroundColor = "steelblue";
    }
  }
}

// Selection Sort
async function selectionSort() {
  const bars = document.getElementsByClassName("bar");
  for (let i = 0; i < array.length - 1; i++) {
    let minIndex = i;
    bars[minIndex].style.backgroundColor = "red";

    for (let j = i + 1; j < array.length; j++) {
      bars[j].style.backgroundColor = "yellow";
      await sleep(100);

      if (array[j] < array[minIndex]) {
        bars[minIndex].style.backgroundColor = "steelblue";
        minIndex = j;
        bars[minIndex].style.backgroundColor = "red";
      } else {
        bars[j].style.backgroundColor = "steelblue";
      }
    }

    if (minIndex !== i) {
      [array[i], array[minIndex]] = [array[minIndex], array[i]];
      bars[i].style.height = array[i] + "px";
      bars[minIndex].style.height = array[minIndex] + "px";
    }
    bars[minIndex].style.backgroundColor = "steelblue";
  }
}

// Insertion Sort
async function insertionSort() {
  const bars = document.getElementsByClassName("bar");
  for (let i = 1; i < array.length; i++) {
    let key = array[i];
    let j = i - 1;

    bars[i].style.backgroundColor = "red";
    await sleep(100);

    while (j >= 0 && array[j] > key) {
      bars[j].style.backgroundColor = "yellow";
      array[j + 1] = array[j];
      bars[j + 1].style.height = array[j + 1] + "px";
      await sleep(100);
      bars[j].style.backgroundColor = "steelblue";
      j--;
    }
    array[j + 1] = key;
    bars[j + 1].style.height = key + "px";
    bars[i].style.backgroundColor = "steelblue";
  }
}

// Merge Sort
async function mergeSort(arr, left, right) {
  if (left >= right) return;

  const mid = Math.floor((left + right) / 2);
  await mergeSort(arr, left, mid);
  await mergeSort(arr, mid + 1, right);
  await merge(arr, left, mid, right);
}

async function merge(arr, left, mid, right) {
  const bars = document.getElementsByClassName("bar");
  const leftArr = arr.slice(left, mid + 1);
  const rightArr = arr.slice(mid + 1, right + 1);

  let i = 0, j = 0, k = left;
  while (i < leftArr.length && j < rightArr.length) {
    bars[k].style.backgroundColor = "red";
    await sleep(100);
    if (leftArr[i] <= rightArr[j]) {
      arr[k] = leftArr[i];
      bars[k].style.height = arr[k] + "px";
      i++;
    } else {
      arr[k] = rightArr[j];
      bars[k].style.height = arr[k] + "px";
      j++;
    }
    bars[k].style.backgroundColor = "steelblue";
    k++;
  }

  while (i < leftArr.length) {
    bars[k].style.backgroundColor = "red";
    arr[k] = leftArr[i];
    bars[k].style.height = arr[k] + "px";
    await sleep(100);
    bars[k].style.backgroundColor = "steelblue";
    i++;
    k++;
  }

  while (j < rightArr.length) {
    bars[k].style.backgroundColor = "red";
    arr[k] = rightArr[j];
    bars[k].style.height = arr[k] + "px";
    await sleep(100);
    bars[k].style.backgroundColor = "steelblue";
    j++;
    k++;
  }
}

// Quick Sort
async function quickSort(arr, low, high) {
  if (low < high) {
    let pi = await partition(arr, low, high);
    await quickSort(arr, low, pi - 1);
    await quickSort(arr, pi + 1, high);
  }
}

async function partition(arr, low, high) {
  const bars = document.getElementsByClassName("bar");
  let pivot = arr[high];
  bars[high].style.backgroundColor = "red";
  let i = low - 1;

  for (let j = low; j < high; j++) {
    bars[j].style.backgroundColor = "yellow";
    await sleep(100);

    if (arr[j] < pivot) {
      i++;
      [arr[i], arr[j]] = [arr[j], arr[i]];
      bars[i].style.height = arr[i] + "px";
      bars[j].style.height = arr[j] + "px";
    }
    bars[j].style.backgroundColor = "steelblue";
  }

  [arr[i + 1], arr[high]] = [arr[high], arr[i + 1]];
  bars[i + 1].style.height = arr[i + 1] + "px";
  bars[high].style.height = arr[high] + "px";
  bars[high].style.backgroundColor = "steelblue";

  return i + 1;
}

generateArray();
</script>

</body>
</html>


## 3. Bubble sort
**Bubble sort** is a simple comparison-based sorting algorithm. it repeatedly compares adjacent elements and swap them if they are in the wrong order. In each iteration the largest element bubbles up to the end of the list. You can visualize it in the given page.

### 3.1 Time & Space Complexity: 
| Time Complexicity |
| ------ | ----------- |
|  Best Case:  | O(n) |
|  Average Case: | O(n²) |
|  Worst Case:  | O(n²) |


| Space Complexicity |
| ------ | ----------- |
|  Best Case:  | O(1) |

### 3.2 Code
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


## 4. Insertion Sort
**Insertion Sort** is a simple comparison based sorting algo. it builds the sorted list one element at a time. It works by taking each element and inserting it into its correct postion within the already sorted part of the array.

### 4.1 Time & Space Complexity: 
| Time Complexicity |
| ------ | ----------- |
|  Best Case:  | O(n) |
|  Average Case: | O(n²) |
|  Worst Case:  | O(n²) |

> best case: O(n) -> when array is already sorted.

| Space Complexicity |
| ------ | ----------- |
|  Best Case:  | O(1) |

### 4.2 Code
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


## 5. Merge Sort

### 5.1 Time & Space Complexity: 
| Time Complexicity |
| ------ | ----------- |
|  Best Case:  | O(n log n) |
|  Average Case: | O(n log n) |
|  Worst Case:  | O(n log n) |


| Space Complexicity |
| ------ | ----------- |
|  Best Case:  | O(n) |

### 5.2 Code
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
## 6. Quick Sort

### 6.1 Time & Space Complexity: 
| Time Complexicity |
| ------ | ----------- |
|  Best Case:  | O(n log n) |
|  Average Case: | O(n log n) |
|  Worst Case:  | O(n²) |


| Space Complexicity |
| ------ | ----------- |
|  Best Case:  | O(log n) |

> take space due to recursion

### 6.2 Code
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

## 7. Selection Sort

### 7.1 Time & Space Complexity: 
| Time Complexicity |
| ------ | ----------- |
|  Best Case:  | O(n²) |
|  Average Case: | O(n²) |
|  Worst Case:  | O(n²) |


| Space Complexicity |
| ------ | ----------- |
|  Best Case:  | O(1) |

### 7.2 Code

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


{{< admonition type=note title="code in javascript" open=false >}}
```js
// javascript code
function selectionSort(arr){
    const n = arr.length;
    for(let i = 0 ; i< n ; i++ ){
        let minIndex = i;
        for(let j = i +1 ; j< n ; j++){
            if(arr[minIndex] > arr[j]){
                minIndex = j;
            }
        }
        if(minIndex != i){
            // swap
            let temp = arr[i];
            arr[i] = arr[minIndex];
            arr[minIndex] = temp;
        }
    }
    return arr;
}

```
{{< /admonition >}}

{{< admonition type=success title="code in java" open=false >}}
```java
// java code
public static void selectionSort(int[] arr){
    int n = arr.length;
    for(int i = 0 ; i< n ; i++ ){
        int minIndex = i;
        for(int j = i+1 ; j< n ; j++){
            if(arr[minIndex] > arr[j]){
                minIndex = j;
                
            }
        }
        if(minIndex != i){
            // Swap
            int temp = arr[j];
            arr[j] = arr[j+1];
            arr[j+1] = temp;
        }
    }
}

```
{{< /admonition >}}

{{< admonition type=warning title="code in python" open=false >}}
```python
# python code
def selectionSort(arr):
    n = len(arr)
    
    for i in range(n):
        minIndex = i
        for j in range(i+1, n):
            if arr[minIndex] > arr[j]:
                minIndex = j;

        if minIndex != i:
            # swap
            arr[j] , arr[j+1] = arr[j+1] , arr[j]

    return arr

```
{{< /admonition >}}


## 8. Comparison
| Algorithm         | Best Use Case / Pros                                               | Cons / Limitations                                         |
|------------------|--------------------------------------------------------------------|-----------------------------------------------------------|
| Bubble Sort       | Simple, easy to implement, works for small or nearly sorted arrays | Very slow for large arrays, O(n²) time                   |
| Insertion Sort    | Efficient for small or nearly sorted arrays                        | O(n²) time for large arrays                                |
| Selection Sort    | Simple, small datasets, in-place                                   | Always O(n²), inefficient for large arrays, unstable     |
| Merge Sort        | Large datasets, stable sort, predictable O(n log n) time           | Uses extra memory O(n)                                     |
| Quick Sort        | Very fast on average, in-place O(log n) space, good cache performance | Worst case O(n²), unstable, pivot choice matters          |

