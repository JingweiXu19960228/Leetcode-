1. Wrong code
class Solution:
    def change(self, amount: int, coins: List[int]) -> int:
        n = len(coins)
        # dp = [[0]*amount for _ in range(n+1)]
        dp = [[0]*(n+1) for _ in range(amount)]
        for i in range(n+1):
            dp[i][0] = 1
        #for cur_num in range(amount):
            #dp[0][cur_num] = 0
        


        for i in range(1,n+1):
            for cur_num in range(amount):
                k = 0
                while cur_num - k*coins[i-1]>=0:
                    dp[i][cur_num] += dp[i-1][cur_num-k*coins[i]]
                    k+=1
        return dp[n][amount]
        
        
