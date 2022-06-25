#1 Right code (from online source):
 ```
 class Solution:
    def findMaxLength(self, nums: List[int]) -> int:
        d = {}
        d[0] = -1
        
        res = 0
        summation = 0
        for i in range(0, len(nums)):
            if nums[i]==0:
                nums[i]=-1 
        for i in range(0, len(nums)):
            summation+=nums[i]
                
            if summation in d:
                res = max(res, i - d[summation])
            else:
                d[summation] = i

        return res 
  ```
  
 #2 Thoughts
 (1). In the beginning, I tried to store ALL the locations corresponding to a accumulative sum, then the values would be a list (Python does not support it because it is mutable). 
 (2). Then I realize that it is only necessary to store the location that an accumulative sum FIRST APPEARS
 
 (3) In the code, if a sum has appeared, then the else statement won't be executed (instead, if statement would be). This guarantees (2)
