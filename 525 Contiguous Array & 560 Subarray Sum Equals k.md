#1 Right code for #525 (from online source):
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
 
 (2). Then I realize that it is only necessary to store the location that an accumulative sum FIRST APPEARS.
 
 (3) In the code, if a sum has appeared, then the else statement won't be executed (instead, if statement would be). This guarantees (2)
 
 
 #3  Comare with the right code for #560
 ```
 class Solution:
    def subarraySum(self, nums: List[int], k: int) -> int:
        d=collections.defaultdict(int)
        summation=0
        res=0
        d[0]=1
        for i in range(len(nums)):
            summation += nums[i]
            if summation-k in d:
                res+=d[summation-k]
            d[summation]+=1
        return res
  ```

 #4 Thoughts
 
 (1). In #560, the keys are still summation, but the values are the total times that a sum has appeared.
 
 (2). d[summation]+=1 is recorded everytime in the for loop, independent of the if statement
