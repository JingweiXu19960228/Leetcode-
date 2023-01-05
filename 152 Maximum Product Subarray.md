1.Wrong code

class Solution:
    def maxProduct(self, nums: List[int]) -> int:
        dp_pos = [1]*len(nums)
        dp_pos[0] = nums[0]
        
        dp_neg = [-1]*len(nums)
        dp_neg[0] = nums[0]
        
        max_product = nums[0]
        
        for i in range(1,len(nums)):
            if nums[i]>0:
                dp[i] = max(dp[i-1]*nums[i],nums[i])
            dp[i] = max(dp_pos(i),dp_neg(i))
            max_product = max(max_product,dp[i])
        
        return max_product
        
