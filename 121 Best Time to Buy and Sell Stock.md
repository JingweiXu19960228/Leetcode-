1. Right code
```
class Solution:
    def maxProfit(self, prices: List[int]) -> int:
        low = 1000000
        profit = -100000
        for price in prices:
            low= min(low,price)
            profit = max(price - low, profit)
        return profit
``` 
            




2. Thought
(1) \
Quotes from Leetcode official solution \
'For every element, we are calculating the difference between that element and the minimum of all the values before that element, \
 and we are updating the maximum profit if the difference thus found is greater than the current maximum profit.' \
 
(2) If the pricing is continuously going down, then in each time, the profit is 0
 
 
