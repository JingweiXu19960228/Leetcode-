1. Right code
```
class Solution:
    def permute(self, nums: List[int]) -> List[List[int]]:
        
        def dfs(nums,res,path):
            if not nums:
                res.append(path)

            for i in range(len(nums)):
                dfs(nums[0:i]+nums[i+1:],res,path+[nums[i]])

        res = []
        dfs(nums,res,[])
        return res
```

2. Thoughts:
(1) Notice that the function 'dfs' does not return anything, but just operate on the variable 'res'
