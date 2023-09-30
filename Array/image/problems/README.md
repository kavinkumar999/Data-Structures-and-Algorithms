# Problems

| Problems    | Soultion  |      
| :------------- |:-------------:| 
| [set Matrix to zeros](https://leetcode.com/problems/set-matrix-zeroes)  | [Here](#1) | 

<br>
<br>
<br>


## <span id="1">Set matrix to zero</span> [Leetcode](https://leetcode.com/problems/set-matrix-zeroes/description/)

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