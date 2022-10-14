1. Right code

class Solution:
    def dfs(self,root,sums,res,path):
        if not root:
            return
          
        if (not root.left) and (not root.right):
            if root.val==sums:
                res.append(path+[root.val])

        self.dfs(root.left,sums-root.val,res,path+[root.val]) 
        self.dfs(root.right,sums-root.val,res,path+[root.val]) 
        
    def pathSum(self, root: Optional[TreeNode], targetSum: int) -> List[List[int]]:
        res = []
        path = []
        
        self.dfs(root,targetSum,res,path)
        return res
        
2. Thoughts
(1). 'Root is none' is also an important base case (line 5-6). Without it, the code would try to reach the children of a null root.
Though I still have not figured it out why
  
