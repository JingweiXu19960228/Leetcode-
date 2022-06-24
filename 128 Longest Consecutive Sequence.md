 #1 Right code (from online source):
 ```
class Solution:
    def longestConsecutive(self, nums: List[int]) -> int:
        nums=set(nums)
        res=0
        for x in nums:
            if x-1 not in nums:
                y=x+1
                while y in nums:
                    y+=1
                res=max(res,y-x)
        return res
  ```
        
        
 #2 Thoughts:
 
(1). The 'if' statement guarantees that x is the smallest number in this subsequence //

(2). Consider the basic case, x cannot form a consecutive sequence with other elements (i.e., x-1, x+1 are not in nums) //
Then the 'while' statement would not be executed, so y-x in this round would be 1

(3) Searching a set takes o(1) times
        
