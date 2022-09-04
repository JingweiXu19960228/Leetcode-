1. Right code


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
