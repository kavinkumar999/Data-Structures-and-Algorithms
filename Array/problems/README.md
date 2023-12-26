# Problems

- [Problems](#problems)
  - [Set matrix to zeroLeetcode](#set-matrix-to-zeroleetcode)
  - [pascals-triangle Leetcode](#pascals-triangle-leetcode)
  - [Sort Colors Leetcode](#sort-colors-leetcode)
  - [Stock Buy and Sell Leetcode](#stock-buy-and-sell-leetcode)
  - [Next Permutation Leetcode](#next-permutation-leetcode)



## Set matrix to zero[Leetcode](https://leetcode.com/problems/set-matrix-zeroes/)

**Brute Force Approach** 

- Intialize the new Array m * n called temp
- Traverse the given array, 
- if we encounter the zero
   - then mark temp array the appropriate row and column into zero

> **Time complexity** is O(n * m)* (n + m) <br>
 **Space complexity**  O(n* m)  // we use extra array


**Better Approach** 

We use hashing instead of a new m*n array. When encountering a zero, we hash the zeroth element to check if all other elements are also zero.


- Intialize the new row[n] and col[m] for hashing
- Traverse the given matrix 
- if we encounter the zero, then mark the row[i] and col[j]
- afterwards we can print according to the hashing array

```java
    int[] row = new int[n]; 
    int[] col = new int[m]; 

    for (int i = 0; i < n; i++) {
        for (int j = 0; j < m; j++) {
            if (matrix.get(i).get(j) == 0) {
                row[i] = -1;
                col[j] = -1;
            }
        }
    }

    for (int i = 0; i < n; i++) {
        for (int j = 0; j < m; j++) {
            if (row[i] == -1 || col[j] == -1) {
                matrix.get(i).set(j, 0);
            }
        }
    }

    return matrix;
```
> **Time complexity** is O(n * m)* (n + m) <br>
 **Space complexity**  O(n* m)  // we use extra array
 

 **Efficient Approach** 

 Instead of hashing into new array, try to hashing into an given array

 ```java
    for (int i = 0; i < n; i++) {
        for (int j = 0; j < m; j++) {
            if (matrix.get(i).get(j) == 0) {
                matrix[i][0] = 0;
                matrix[0][j] = 0;
            }
        }
    }

    for (int i = 0; i < n; i++) {
        for (int j = 0; j < m; j++) {
            if (matrix[i][0] == 0 || matrix[0][j] == 0) {
                System.out.print(0)
            } else {
                System.out.print(matrix[i][j])
            }
        }
    }

    return matrix;
```
## pascals-triangle [Leetcode](https://leetcode.com/problems/pascals-triangle/)

![pascal](../image/pascals.gif)

Questions could arise from 
 - return all the arrays in the pascal's triangle
 - return the specificed index from the pascal's triangle

**Better Approach** 

- Intialize the new **result[][]**
- Traverse using the giving **numRows**
- find the left and right value in the sub loop
- append value into the result array

```java
    List<List<Integer>> result = new ArrayList<>();
    for(int i=0; i<numRows; i++) {
        List<Integer> test = new ArrayList<Integer>(i+1);
        test.add(1);
        int n = test.size();
        for(int j=1;j <i; j++ ){
            int left = result.get(i-1).get(j-1);
            int right = result.get(i-1).get(j);
            test.add(left + right);
        }
        if(i!=0) test.add(1);
        result.add(test);
    }


    return  result;
```
> **Time complexity** is O(n * 2) <br>
 **Space complexity**  O(n * 2)
 
## Sort Colors [Leetcode](https://leetcode.com/problems/sort-colors/)


**Brute Force Approach** 

we have only 3 digits, so better to intialize three variables and count all the digits and iterate and print in sorted order

> **Time complexity** is O(n) <br>
 **Space complexity**  O(1)
 
**Efficient Approach** 

- Initialize the three pointer low , high and traverseral pointer
- traversal using the **traverseral pointer** <= **high**
    - if element is 0 
        - swap with low and traversal pointer
    - if element is 1
        - let it be
    - if element is 2
        - swap with high and traversla pointer

- return array


```java
    int low = 0;
    int traversePointer = 0;
    int high = nums.length - 1;
    for(int i=0;i < nums.length; i++) {
        if(nums[traversePointer] == 0) {
            swap(nums, low, traversePointer);
            low++;
            traversePointer++;
        }
        else if(nums[traversePointer] == 1)
        {
            traversePointer++;
        }
        else {
            swap(nums, traversePointer, high);
            traversePointer++;
            high--;
        }
    }
```
> **Time complexity** is O(n) <br>
 **Space complexity**  O(1)
 
## Stock Buy and Sell [Leetcode](https://leetcode.com/problems/best-time-to-buy-and-sell-stock/)


**Brute Force Approach** 

- Initialize the two array leftWiseMin[] and rightWisemax[]
- find the both side min and max and store the array
- finally return the max of  rightwiseMax[i] - leftWiseMin[i]

```java
    int[] rightMin = new int[prices.length];
    int[] leftMax = new int[prices.length];
    int leftpivot = 0;
    int rightpivot = prices.length - 1;
    for(int i=0;i<prices.length; i++) {
        if(prices[leftpivot] > prices[i]) {
            leftpivot = i;
        }
        rightMin[i] = prices[leftpivot];
    }
    for(int i=prices.length -1 ;i >=0; i--) {
        if(prices[rightpivot] < prices[i]) {
            rightpivot = i;
        }
        leftMax[i] = prices[rightpivot];
    }

    int result = 0;
    for(int i=0;i<prices.length;i++) {
        int tempMax = leftMax[i] - rightMin[i];
        if(tempMax > result) {
            result = tempMax;
        }
    }
    return result;

```


> **Time complexity** is O(n) <br>
 **Space complexity**  O(n)
 
**Efficient Approach** 

Before we use some extra array space; now we optimise it furuther

- Traverse the given arrary; find the min
- max = currentindex - min
- return the max


```java
    int lsf = Integer.MAX_VALUE;
    int result = 0;
    int pivot = 0;
    
    for(int i = 0; i < prices.length; i++){
        if(prices[i] < lsf){
            lsf = prices[i];
        }
        pivot = prices[i] - lsf;
        if(result < pivot){
            result = pivot;
        }
    }
    return result;
```
> **Time complexity** is O(n) <br>
 **Space complexity**  O(1)
 
 ## Next Permutation [Leetcode](https://leetcode.com/problems/next-permutation/)


**Efficient Approach** 

![permutation](../image/next-permutation-algorithm.svg)

```java
    int initialPointer = nums.length - 1;
    int firstSmall = -1;

    while(initialPointer > 0)
    {
        if(nums[initialPointer] > nums[initialPointer - 1])
        {
            firstSmall = initialPointer - 1;
            break;
        }
        initialPointer--;
    }
    if(firstSmall != -1) {
        int rightMax = -1;
        initialPointer = nums.length - 1;
        while(initialPointer > firstSmall)
        {
            if(nums[initialPointer] > nums[firstSmall])
            {
                rightMax = initialPointer;
                break;
            }
            initialPointer--;
        }
        if(rightMax != -1) {
            swap(nums, firstSmall, rightMax);
            firstSmall ++;
            int high = nums.length - 1;

            while(firstSmall < high) {
                swap(nums, firstSmall, high);
                firstSmall++;
                high--;
            }

        }

    } else {
        int low = 0;
        int high = nums.length -1;
        while(low < high) {
            swap(nums, low, high);
            low++;
            high--;
        }
    }
    public  static void swap(int[] nums, int i, int j){
        int temp = nums[i];
        nums[i] = nums[j];
        nums[j] = temp;
    }
```
> **Time complexity** is O(n) <br>
 **Space complexity**  O(1)
 