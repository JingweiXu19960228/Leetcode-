

1. Right code
```
class Solution:
    def findLeaves(self, root: Optional[TreeNode]) -> List[List[int]]:
        
        res = collections.defaultdict(list)
        
        def dfs(root):
            if not root:
                return -1
            l = dfs(root.left)
            r = dfs(root.right)
            
            depth = max(l,r)+1     
            
            res[depth].append(root.val)            
            return depth
        
        dfs(root)
        return res.values()

```



2. Thoughts:

(1). Think about the example https://leetcode.com/problems/find-leaves-of-binary-tree/

Go through the code line by line to see how node 4,5,3 (leaves) are added at res[depth = 0]

Then think about how node 2 is added at res[depth = 1]
