# Array
An array is a collection of items of same data type stored at contiguous memory locations. This makes it easier to calculate the position of each element by simply adding an offset to a base value, i.e., the memory location of the first element of the array (generally denoted by the name of the array).

![array](image/array.png)<br>
Array is similiar to defining any other variables.<br>
*Two things need to be done while initialize the array*<br>
- Datatype of the array
- Size of the array
> Array size cannot be change dynamically<br>

**Advantages of the array**
 - Arrays allow random access of elements. This makes accessing elements by position faster.
 - Arrays have better cache locality that can make a pretty big difference in performance.
 - Arrays are best for storing multiple values in a single variable

 `char arr1[] = {'g', 'e', 'e', 'k', 's'};`<br>
 `int arr2[] = {10, 20, 30, 40, 50};`<br>
 `For example arr1[0] gives us 'g'`<br>
 `arr2[3] gives us 40.`<br>
<h1 align="center">Basic array operations</h1>

## Searching in an array
Searching an element in an array means to check if a given element is present in an array or not. This can be done by accessing elements of the array one by one starting from the first element and checking if any of the element matches with the given element.
> we can use loops to iterate each element one by one and search given element

### Algorithm for searching
```python
for(i to n):
    if(arr[i] == searching element):
        print("Element found")
    else:
        print("Element not found")
```
> **Time complexity** for the algorithm is O(N)
---

## Inseration in array

Given an array of a given size. The task is to insert a new element in this array. There are two possible ways of inserting elements in an array:
- Insert elements at the end of the array.
- Insert element at any given index in the array.

> A special case is needed to be considered is that whether the array is already full or not. If the array is full, then the new element can not be inserted.


`len ----> number of elements occupied`<br>
`N ------> Size of the array`<br>
`K ------> new element to be inserted`<br>

### Insert element at the end of the array
`Algorithm` <br>
1. First step to check whether the array has empty space or not
```python
if(len < N):
    // space left
else:
    // array is full
```
2. If there is any empty space; insert the element into len+1 index

```python
arr[len + 1] = k
```
> **Time complexity** for the algorithm is O(1)

### Insert element at given index in the array
`Algorithm`
1. First step to check whether the array has empty space or not
```python
if(len < N):
    // space left
else:
    // array is full
```
2. If there is empty space, shift all the elements into right by 1 from the specified index
```python
for(i = len-1, i >= idx, i--):

    arr[i+1] = arr[i]

```
3. After shifting the elements, place the element K at index idx.
```python
arr[idx] = K

```
> **Time complexity** for the algorithm is O(N)

---

## Deletion in Arrays
To delete a given element from an array, we will have to first search the element in the array. If the element is present in the array then delete operation is performed for the element otherwise the user is notified that the array does not contains the given element.

`Alogrithm`<br>
1. First check the given element is present in the array or not
```python
for(i = 0, i < N, i++):

    if(arr[i] == K):
        idx = i
        return
    else:
        Element not Found


```
2. Now, to delete the element present at index idx, left shift all of the elements present after idx by one place and finally reduce the length of the array by 1.

```python
for(i = idx+1, i < len, i++):

    arr[i-1] = arr[i]


len = len-1


```
> **Time complexity** for the algorithm is O(N)
---
## problems

| Problems    | solution          
| :------------- |:-------------:| 
| Reverse the arrary    | [Here]() | 
| Sliding window Technique     | [Here]() | 
| Binary array Sorting | [Here]() |
| Prefix array sum | [Here]() |
| Container with most water | [Here]() |
| Equilibrium Point | [Here]() |
| Find duplicates in the array | [Here]() |
| Frequencies of Limited Range Array Elements | [Here]() |
| Intersection of two arrays | [Here]() |
| Kedane's Algorithm | [Here]() |
| Max and second Max of the array | [Here]() |
| Max circular subarray sum  | [Here]() |
| Maximum index  | [Here]() |
| Maximum sum in configuration  | [Here]() |
| Maximum sum path in two arrays  | [Here]() |
| Minimum distance between two numbers  | [Here]() |
| Mountain subarray problem  | [Here]() |
| Overlapping intervals  | [Here]() |
| Product array puzzle   | [Here]() |
| Rearrange an array with O(1) extra space   | [Here]() |
| Remove duplicates in small prime array   | [Here]() |
| Replace all 0's with 5   | [Here]() |
| Rotate Array   | [Here]() |
| Sorted subsequence of size 3  | [Here]() |
| Stickler Thief   | [Here]() |
| Subarray with given sum   | [Here]() |
| Third largest element  | [Here]() |
| Three Sum Closest   | [Here]() |
| Trapping Rain Water   | [Here]() |
| Union of Two Sorted Arrays   | [Here]() |
| Wave Array   | [Here]() |