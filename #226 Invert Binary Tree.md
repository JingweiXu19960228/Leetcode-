#1 WRONG CODE (1st attempt): 
```
class Solution:
    def invertTree(self, root: Optional[TreeNode]) -> Optional[TreeNode]:
        def helper(node:Optional[TreeNode])-> Optional[TreeNode]:
                
            cur_node=node
            if node!=None:
                cur_node.right=helper(node.left)
                cur_node.left=helper(node.right)
                return cur_node
                
        return helper(root)
 ```
 
 
 
 #2 Right code:
 ```
 class Solution:
    def invertTree(self, root: Optional[TreeNode]) -> Optional[TreeNode]:
        if root!=None:
            root.right,root.left=self.invertTree(root.left),self.invertTree(root.right)

        return root
  ```
  
  In the 1st attempt, by combining line 9 and 10 would lead to correct results in Leetcode
