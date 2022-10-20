1. Wrong code

```
class Solution:
    def diameterOfBinaryTree(self, root: Optional[TreeNode]) -> int:
        
        def height(root):
            if not root:
                return 0
            self.res = max(res,height(root.left)+height(root.right))
            return max(height(root.left),height(root.right))+1
        
        
        res = 0
        
        height(root)
        return res
```


2. Right code
class Solution: 
res = 0
    def diameterOfBinaryTree(self, root: Optional[TreeNode]) -> int:
        
        def height(root):
            if not root:
                return 0
            l = height(root.left)
            r = height(root.right)
            self.res = max(self.res,l+r)
            return max(l,r)+1
        
        
        height(root)
        return self.res
        
3. Thoughts
(1). I don't understand the varialbe res, why it is defined outside the function height
(2). In the right code, r and l is first calculated, otherwise the time limit would be exceeded. I don't know why


