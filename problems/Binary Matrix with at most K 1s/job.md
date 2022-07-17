[<img src="./Difficulty-Medium-yellow.svg">](#)

# Binary Matrix with at most K 1s

Given a binary matrix **M** with **R** rows and **C** columns, where each element of the matrix will be 0 or 1. Find the largest square that can be formed with center **(i, j)** and contains at most **K** 1’s. There are Q queries, a single query has two integers denoting the centre (i,j) of the square.  

__Example 1:__  

> **Input:**  
> R = 4, C = 5  
> M = {{1, 0, 1, 0, 0}  
> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{1, 0, 1, 1, 1}  
> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{1, 1, 1, 1, 1}  
> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{1, 0, 0, 1, 0}}  
> K = 9, Q = 1  
> q_i[] = {1}  
> q_j[] = {2}  
> **Output:**  
> 3  
> **Explanation:**  
> Maximum length square with center at (1, 2) that can be formed is of 3 length from (0, 1) to (2, 4).  

__Example 2:__  
> **Input:**  
> R = 3, C = 3  
> M = {{1, 1, 1}  
> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{1, 1, 1}  
> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{1, 1, 1}}  
> K = 9, Q = 2  
> q_i[] = {1, 2}  
> q_j[] = {1, 2}  
> **Output:**  
> 3 1  

__Your Task:__  
You don't need to read input or print anything. Your task is to complete the function **largestSquare()** which takes 2 integers R, and C followed by a list of lists M denoting the binary matrix and then three integers i,j, and K as input and returns a list of integers denting the largest Square possible for each query.  

__Expected Time Complexity:__ O(R*C + Q*log(MIN_DIST)), where MIN_DIST is the minimum distance of the center from the edges of the matrix where MIN_DIST is the minimum distance of the center from the edges of the matrix.  
__Expected Auxiliary Space:__ O(R*C)  

__Constraints:__  
1 ≤ R,C ≤ 500  
1 ≤ Q ≤ 104  
0 ≤ K ≤ R*C  
0 ≤ i < R  
0 ≤ j < C  

__Solution:__  
```python

```