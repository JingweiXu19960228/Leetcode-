    1. Wrong code (time limit exceeded, but passed initial test)
    def rob(self, root: Optional[TreeNode]) -> int:
        
        if not root:
            return 0
        if (not root.right) and (not root.left):
            return root.val
        if (not root.right) and (root.left):
            return max(self.rob(root.left),root.val+self.rob(root.left.left)+self.rob(root.left.right))
        if (not root.left) and (root.right):
            return max(self.rob(root.right),root.val+self.rob(root.right.left)+self.rob(root.right.right))
        
        rob1 = root.val + self.rob(root.left.left)+self.rob(root.left.right)+self.rob(root.right.left)+self.rob(root.right.right)
        rob2 = self.rob(root.left)+self.rob(root.right)
        
        return max(rob1,rob2)
        
