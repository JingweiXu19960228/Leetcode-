1. Right code
class Solution:
    def change(self, amount: int, coins: List[int]) -> int:

        n = len(coins)
        dp = [[0]*n for _ in range(amount+1)]
        for j in range(n):
            dp[0][j] = 1
        
        for i in range(1,amount+1):
            for j in range(n):
                x = dp[i-coins[j]][j] if i>=coins[j] else 0 
                y = dp[i][j-1] if j>=1 else 0
                dp[i][j] = x+y

        return dp[amount][n-1]
        

2. Thought
(1). Notice the boundary condition dp[0][j] = 1 for j in range(n).
It would make sense if you think about the expression of x

(2). the 1st index changes from 1 to amount, while the 2nd index changes form 0 to n-1. I still don't know why
