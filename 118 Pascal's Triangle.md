1. Wrong code
 ```
class Solution:
    def generate(self, numRows: int) -> List[List[int]]:
        def helper(k):
            if k == 1:
                return [[1]]
            
            lastTriangle = helper(k-1)
            lastRow= lastTriangle[k-2]

            newRow = [1]

            for i in range(len(lastRow)-1):
                newRow.append(lastRow[i]+lastRow[i+1])
            newRow.append(1)

            return helper(k-1).append(newRow)
        return helper(numRows)
```                

2. Right code
class Solution:
    def generate(self, numRows: int) -> List[List[int]]:
        t = []
        for n in range(numRows):
            row = [None for _ in range(n+1)]
            row[0] = 1
            row[-1] = 1
            for j in range(1,n):
                row[j] = t[n-1][j-1] + t[n-1][j]           
            t.append(row)
        return t
 ```            

3. Thoughts
(1). I have no idea why my origina code cannot work. The error says  line 9 returns NoneType ('lastTriangle')
