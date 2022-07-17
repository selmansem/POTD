[<img src="./Difficulty-Easy-green.svg">](#)

# Find all possible paths from top to bottom  

Given a N x M grid. Find All possible paths from top left to bottom right.From each cell you can either move only to right or down.  

__Example 1:__  
> **Input:**  
> 1 2 3  
> 4 5 6  
> **Output:**  
> 1 4 5 6  
> 1 2 5 6  
> 1 2 3 6  
> **Explanation:**  
> We can see that there are 3 paths from the cell (0,0) to (1,2).  

__Example 2:__  
> **Input:**  
> 1 2  
> 3 4  
> **Output:**  
> 1 2 4  
> 1 3 4  

__Your Task:__  
You don't need to read input or print anything. Your task is to complete the function **findAllPossiblePaths()** which takes two integers n,m and grid[][]  as input parameters and returns all possible paths from the top left cell to bottom right cell in a 2d array.  

__Expected Time Complexity:__ O(2^N*M)  
__Expected Auxiliary Space:__ O(N)  

__Constraints:__  
1 <= n,m <= 10  
1 <= grid[i][j] <= n*m  
n * m < 20  

__Solution:__  
```python
from typing import List
class Solution:
    def calculate(self,n,m,i,j,ans,temp,grid):
        if(i>=n or j>=m):
            return
        temp.append(grid[i][j])
        
        if(i==n-1 and j==m-1):
            ans.append(temp[:])
       
        self.calculate(n,m,i+1,j,ans,temp,grid)
        self.calculate(n,m,i,j+1,ans,temp,grid)
        temp.pop()
        
    def findAllPossiblePaths(self, n : int, m : int, grid : List[List[int]]) -> List[List[int]]:
        ans=[]
        temp=[]
        self.calculate(n,m,0,0,ans,temp,grid)
        return ans
```