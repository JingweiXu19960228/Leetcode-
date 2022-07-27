1. Right code
```
class Solution:
    def canJump(self, nums: List[int]) -> bool:
        reach = 0
        for i in range(len(nums)):
            if i> reach:
                return False
            sums = i+nums[i]
            reach = max(reach, sums)
        return True
```

2. Thoughts

(1). Notice that the 'if' statement is executed before the 'reach' variable is updated

(2). There are two equivalence

a.  If for any i, i<=reach, then return true

b. If there exists an i so that i > reach, then return false

a is a little bit hard to understand

