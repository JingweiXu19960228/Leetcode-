1. Right code

```
class Solution:
    def jump(self, nums: List[int]) -> int:
        pos = 0
        count = 0
        cur = 0
        
        while(cur<len(nums)-1):
            count+= 1
            pre = cur
            while (pos<=pre):
                cur = max(pos+nums[pos],cur)
                pos+=1
        return count
 ```
 
 
 
 2. Thoughts
 
 (1). 'Pre' is the current 'cur', while 'pos' is the previous 'cur' (why?)
 
 (2). Notice the boundaries. For example 'cur < len(nums)-1', rather than '<=', because when cur = len(nums)-1, it already reach the end of the array
