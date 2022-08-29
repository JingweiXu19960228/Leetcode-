1. Wrong code

class Solution:
    def nextPermutation(self, nums: List[int]) -> None:
        """
        Do not return anything, modify nums in-place instead.
        """
        if nums==sorted(nums,reverse=True):
            return 1
        if (len(nums)>1):
            i=len(nums)-1
            n=len(nums)-1
            if (nums[i-1]<nums[i]):
                nums[i],nums[i-1]=nums[i-1],nums[i]
            else:
                while (i>0) and (nums[i-1]>nums[i]):
                    i-=1                  
                i-=1
                j=i+1
                while (nums[j]>nums[i]) and (j<n):
                    j+=1
                nums[i],nums[j-1]=nums[j-1],nums[i]
                nums[i+1:n]=reversed(nums[i+1:n])
            
