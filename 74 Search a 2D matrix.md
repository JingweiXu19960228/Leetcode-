1. Right code (20221106, 2nd)
```
class Solution:
    def searchMatrix(self, matrix: List[List[int]], target: int) -> bool:        
        height = len(matrix)
        width = len(matrix[0])
        
        top = 0
        bottom = height-1
        
        while top<=bottom:
            mid = top + (bottom-top)//2
            
            if matrix[mid][0]>target:
                bottom = mid-1
                
            else:
                top = mid+1
        
        row = top
        
        for column in range(width):
            if matrix[row-1][column]==target:
                return True
        return False
  ```
  
  2. Thoughts
  
  'row' is the smallest value so that matrix[row][0]>target, so it merans that matrix[row-1][0]<=target.
  
  So if there is a solution, it has to be in the row-1
