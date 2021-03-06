[<img src="./Difficulty-Hard-red.svg">](#)

# Partition array to K subsets

Given an integer array **a[ ]** of **N** elements and an integer **K**, the task is to check if the array **a[ ]** could be divided into **K** non-empty subsets with equal sum of elements.  
__Note:__ All elements of this array should be part of exactly one partition.

__Example 1:__
  
> **Input:**  
> N = 5  
> a[] = {2,1,4,5,6}  
> K = 3  
> **Output:**  
> 1  
> **Explanation:** we can divide above array into 3 parts with equal sum as (2, 4), (1, 5), (6).  

__Example 2:__

> **Input**  
> N = 5  
> a[] = {2,1,5,5,6}  
> K = 3  
> **Output:**  
> 0  
> **Explanation:** It is not possible to divide above array into 3 parts with equal sum.

__Your Task:__  
You don't need to read input or print anything. Your task is to complete the function **isKPartitionPossible()** which takes the array a[], the size of the array N, and the value of K as inputs and returns true (same as 1) if possible, otherwise false (same as 0).

__Expected Time Complexity:__ O(N*2<sup>N</sup>).  
__Expected Auxiliary Space:__ O(2<sup>N</sup>).  

__Constraints:__  
1 ≤ K ≤ N ≤ 10  
1 ≤ a[i] ≤ 100  

__Solution:__  
```python
class Solution:
    def isKPartitionPossible(self, a, k):
            a.sort()
            target, rem = divmod(sum(a), k)
            if rem or a[-1] > target:
                return False
            dp = [False] * (1 << len(a))
            dp[0] = True
            total = [0] * (1 << len(a))
    
            for num_actual in range(1 << len(a)):
                if not dp[num_actual]:
                    continue
                for i, num in enumerate(a):
                    num_futu = num_actual | (1 << i)
                    if num_actual != num_futu and not dp[num_futu]:
                        if (num <= target - (total[num_actual] % target)):
                            dp[num_futu] = True
                            total[num_futu] = total[num_actual] + num
                        else:
                            break
            return dp[-1]
```