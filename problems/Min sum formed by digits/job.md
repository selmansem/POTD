[<img src="./Difficulty-Easy-green.svg">](#)

# Min sum formed by digits

Given an array of digits (values are from 0 to 9), find the minimum possible sum of two numbers formed from digits of the array. All digits of given array must be used to form the two numbers.

__Example 1:__
  
> **Input:**  
> N = 6  
> arr[] = {6, 8, 4, 5, 2, 3}  
> **Output:**  
> 604  
> **Explanation:**  
> The minimum sum is formed by numbers  
> 358 and 246  

__Example 2:__
  
> **Input:**  
> N = 5  
> arr[] = {5, 3, 0, 7, 4}  
> **Output:**  
> 82  
> **Explanation:**  
> The minimum sum is formed by numbers  
> 35 and 047  

__Your Task:__  
You **don't** have to print anything, printing is done by the driver code itself. Your task is to complete the function **minSum()** which takes the array **A[]** and its size **N** as inputs and returns the required sum.  

__Expected Time Complexity:__ O(N. log(N))  
__Expected Auxiliary Space:__ O(1)

__Constraints:__  
1 ≤ N ≤ 35  
0 ≤ A[] ≤ 9  

__Solution:__  
```python
class Solution:
    def minSum(self, arr, n):
        # Check if we have no numbers. If yes, return 0
        if n == 0:
            return 0
        arr.sort() # To make sure that the smallest number is at the beginning of the array
        num_uno = ""
        num_dos = ""
        # We will take the first number from the array, add it to the number we are building and remove it from the array. Repeat this process until the array is empty.
        while len(arr) > 0:
            num_uno = num_uno + str(min(arr))
            arr.remove(min(arr))
            # To check if the array is already empty, we will check if the length of the array is 0. If it is, we will break the loop.
            if len(arr) == 0:
                # If @num_dos is also empty means that we have only one number in the array. We will add a 0 to make the sum possible.
                if len(num_dos) == 0:
                    num_dos = num_dos + str(0)
                break
            num_dos = num_dos + str(min(arr))
            arr.remove(min(arr))
            
        return int(num_uno) + int(num_dos)
```