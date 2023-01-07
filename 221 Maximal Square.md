1. Right code

class Solution:
    def maximalSquare(self, matrix: List[List[str]]) -> int:
        m = len(matrix)
        n = len(matrix[0])
        res = 0
        if not matrix:
            return 0

        dp = [[0]*(n+1) for _ in range(m+1)]

        for i in range(1,m+1):
            for j in range(1,n+1):
                if matrix[i-1][j-1]=='1':
                    dp[i][j] = min(dp[i-1][j],dp[i][j-1],dp[i-1][j-1])+1
                    res = max(dp[i][j],res)
        return res*res
 
 2. Thought
 (1). The key is to understand the dp condition (line 16)
 
 (2). Notice that the size of the dp is 1 larger than matrix
 dp [i][j] corresponds to the largest box that can be formed within matrix[0:i-1][0:j-1]
 The 1st row and the 1st column of dp are not used
