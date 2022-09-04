1. Right code

```
class Solution:
    def minOperations(self, nums: List[int], x: int) -> int:
        
        i = 0
        target = sum(nums) - x
        if target<0:
            return -1
        if target==0:
            return len(nums)
        
        summation = 0
        maximum = 0
        for j in range(len(nums)):
            summation+=nums[j]
            
            while (summation > target):
                summation-= nums[i]
                i+=1
            if summation == target:
                maximum = max(maximum,(j-i+1))
                
        if maximum==0:
            return -1
        else:
            return len(nums) - maximum
 ```
 
 
 2. Thoughts
 
 (1). This problem is equivalent to find the maximum subarray so that the sum is target = sum(nums) - x
 
 (2). Notice that target can be smaller than or equal to 0. Only when it is larger than 0 then it makes sense
 
 
