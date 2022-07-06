Wrong code

class Solution:
    def maxSubArray(self, nums: List[int]) -> int:
        if len(nums)==0:
            return 0
        else:
            return max( self.maxSubArray(nums[:len(nums)-1]) + nums[-1] , nums[-1])

