
# Intuition for Kadane’s Algorithm

> The maximum sub-array sum is finding out the sub-array which has the maximum sum.


## Problem
[Maximum SubArray](https://leetcode.com/problems/maximum-subarray)

Questions could arise from 
 - return the index for the starting and ending maximum subarray
 - return the sum of the maximum subarray

> If we encounter the negative numbers discard it and mark the sum into 0


 ## Pseudocode

 - Initialize:
    - max = INT_MIN
    - sum = 0

- Loop for each element of the array

  - sum = sum + a[i]
  - if(max < sum)
    - max = sum
  - if(sum < 0)
    - sum = 0
- return max

**Time complexity** for the algorithm is θ(N) <br>
**Space complexity** for the algorithm is θ(1)