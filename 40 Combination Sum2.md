1. Right code
```
class Solution:
    def combinationSum2(self, candidates: List[int], target: int) -> List[List[int]]:
        def dfs(nums,target,index,path,res):
            if target<0:
                return
            if target==0:
                res.append(path)
                
            for i in range(index,len(nums)):
                if i>index and nums[i]==nums[i-1]:
                    continue
                dfs(nums,target-nums[i],i+1,path+[nums[i]],res)
            
        res = []
        candidates.sort()
        dfs(candidates,target,0,[],res)
            
        return res
 ```
 
 2. Thoughts
 
 (1). Plase not thtat, when call the dfs recursively (line 14), the index is i+1
 
 (2). It is hard to understand the purpose of line 12-13
 
Think about the case [2,2,3] and 5. If we can use the 1st '2' with 3 to make 5, then the combination of 2nd '2' with 3 would be ruled out due to line 12-13
