1. Right code
```
class Solution:
    def rotate(self, nums: List[int], k: int) -> None:
        """ Do not return anything, modify nums in-place instead. """
        def rev(nums, l, r):
            while l < r:
                nums[l], nums[r] = nums[r], nums[l]
                l += 1
                r -= 1
        
        n = len(nums)
        k %= n
        rev(nums, 0, n - 1)
        rev(nums, 0, k - 1)
        rev(nums, k, n - 1)
``` 
        
        
        
2. My code (should be right, too)
```
class Solution:
    def rotate(self, nums: List[int], k: int) -> None:
        """
        Do not return anything, modify nums in-place instead.
        """
        
        def reverse(nums):
            return nums[::-1]

        ind = len(nums) - k
        print(reverse(reverse(nums[:ind])+reverse(nums[ind:])))
```

3. Thoughts
(1). In the online solution, two pointer is used when reversing the array (luckily, Python has built-in ,ethod for reversing array) 
