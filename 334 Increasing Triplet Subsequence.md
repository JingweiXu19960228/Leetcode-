1. Right code

```
class Solution:
    def increasingTriplet(self, nums: List[int]) -> bool:
        first = float('inf')
        second = float('inf')
        for num in nums:
            if num <= first:
                first = num
            elif num <= second:
                second = num
            else:
                return True
        return False
 ```
        
        
2. Thoughts

(1). Noitce that these first and second is NOT the largest two element!  

(2). This code looks easy, but very hard to understand. There is a good explanation in the youtube video (https://www.youtube.com/watch?v=41gyzVIx-ds)
Please go to at around 5min

(3). Notice that the if else statement is '<=' rather than '<'. It would be easy to understand if we consider an array with all same numbers, for e.g [1,1,1,1,1]
Using '<' instead of '<=' would return True. However, it should return False for this array.

