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
## Problems

| Problems    | Soultion  |      
| :------------- |:-------------:| 
| Reverse the arrary    | [Here](https://www.geeksforgeeks.org/write-a-program-to-reverse-an-array-or-string/) |  
| Sliding window Technique     | [Here](https://www.geeksforgeeks.org/window-sliding-technique/) |  
| Binary array Sorting | [Here](https://practice.geeksforgeeks.org/problems/binary-array-sorting-1587115620/1) | 
| Prefix array sum | [Here](https://www.geeksforgeeks.org/prefix-sum-array-implementation-applications-competitive-programming/) | 
| Container with most water | [Here](https://leetcode.com/problems/container-with-most-water/) | 
| Equilibrium Point | [Here](https://practice.geeksforgeeks.org/problems/equilibrium-point-1587115620/1) | 
| Find duplicates in the array | [Here](https://www.geeksforgeeks.org/find-duplicates-given-array-elements-not-limited-range/) | 
| Frequencies of Limited Range Array Elements | [Here](https://www.geeksforgeeks.org/find-frequency-of-each-element-in-a-limited-range-array-in-less-than-on-time/) | 
| Intersection of two arrays | [Here](https://leetcode.com/problems/intersection-of-two-arrays/) | 
| Kedane's Algorithm | [Here](https://leetcode.com/problems/maximum-subarray/discuss/369797/kadanes-algorithm-with-detailed-explanation-and-example-python) | 
| Max and second Max of the array | [Here](https://www.geeksforgeeks.org/find-second-largest-element-array/) | 
| Max circular subarray sum  | [Here](https://www.geeksforgeeks.org/maximum-contiguous-circular-sum/) | 
| Maximum index  | [Here](https://www.geeksforgeeks.org/given-an-array-arr-find-the-maximum-j-i-such-that-arrj-arri/) | 
| Maximum sum in configuration  | [Here](https://www.geeksforgeeks.org/maximum-sum-iarri-among-rotations-given-array/) | 
| Maximum sum path in two arrays  | [Here](https://www.geeksforgeeks.org/maximum-sum-path-across-two-arrays/) | 
| Minimum distance between two numbers  | [Here](https://www.geeksforgeeks.org/find-the-minimum-distance-between-two-numbers/) | 
| Mountain subarray problem  | [Here](https://www.geeksforgeeks.org/find-whether-subarray-form-mountain-not/) | 
| Overlapping intervals  | [Here](https://www.geeksforgeeks.org/maximum-number-of-overlapping-intervals/) | 
| Product array puzzle   | [Here](https://www.geeksforgeeks.org/a-product-array-puzzle/) | 
| Rearrange an array with O(1) extra space   | [Here](https://www.geeksforgeeks.org/rearrange-given-array-place/) | 
| Remove duplicates in small prime array   | [Here](https://www.geeksforgeeks.org/remove-duplicates-from-an-array-of-small-primes/) | 
| Replace all 0's with 5   | [Here](https://www.geeksforgeeks.org/replace-0-5-input-integer/) | 
| Rotate Array   | [Here](https://www.geeksforgeeks.org/array-rotation/) | 
| Sorted subsequence of size 3  | [Here](https://www.geeksforgeeks.org/sorted-subsequence-size-3-linear-time-using-constant-space/) | 
| Stickler Thief   | [Here](https://practice.geeksforgeeks.org/problems/stickler-theif-1587115621/1) | 
| Subarray with given sum   | [Here](https://www.geeksforgeeks.org/find-subarray-with-given-sum/) | 
| Third largest element  | [Here](https://www.geeksforgeeks.org/third-largest-element-array-distinct-elements/) | 
| Three Sum Closest   | [Here](https://www.geeksforgeeks.org/find-a-triplet-in-an-array-whose-sum-is-closest-to-a-given-number/) | 
| Trapping Rain Water   | [Here](https://www.geeksforgeeks.org/trapping-rain-water/) | 
| Union of Two Sorted Arrays   | [Here](https://www.geeksforgeeks.org/union-and-intersection-of-two-sorted-arrays-2/) | 
| Wave Array   | [Here](https://www.geeksforgeeks.org/sort-array-wave-form-2/) | 