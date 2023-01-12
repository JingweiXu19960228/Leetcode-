1. Right code
 ```
class Solution:
    def numDecodings(self, s: str) -> int:
        dp = [0]*(len(s)+1)
        dp[0] = 1
        for i in range(1,len(dp)):
            if int(s[i-1])!=0:
                dp[i] = dp[i-1]
            if i!=1 and s[i-2:i]>'09' and s[i-2:i]<'27':
                dp[i]+=dp[i-2]
        return dp[-1]
 ```
        
        
2. Thought
(1). Please notice its similarity to the problem 'climb stairs'

(2). The size of the dp array is 1 larger than needed. This is typical for many dp problems

(3). In the 2nd if statement, we need to have 'i!=1', otherwise it would be wrong
