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


