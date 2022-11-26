1. Right code

```
class Solution:
    def maxDepth(self, root: Optional[TreeNode]) -> int:


        q = collections.deque([root])
        
        depth = 0
        while (q):
            l =len(q)
            
            while l>0:
                node = q.popleft()
                if node:
                    q.append(node.left)
                    q.append(node.right)
                l=l-1
            depth+=1
            
        return depth-1
 ```
 
 
 2. Thoughts
 (1). 
