1. Right code
```
class Solution:
    def combinationSum(self, candidates: List[int], target: int) -> List[List[int]]:
        def dfs(nums,target,index,path,res):
            if target<0:
                return
            if target == 0:
                res.append(path)
                return 
            
            for i in range(index,len(nums)):
                dfs(nums,target-nums[i],i,path+[nums[i]],res)
        res = []   
        candidates.sort()
        dfs(candidates,target,0,[],res)
        return res
```        
2. Thoughts

(1). It is still hard for me to understand the purpose of sorting (line 15), and the for loop in the dfs function (line 12-13)

(2). Think about the simplest case, candiates = [a], target=a
