1. Right code
```
class Solution:
    def eraseOverlapIntervals(self, intervals: List[List[int]]) -> int:
        intervals.sort(key = lambda x:x[1])
        first_end = intervals[0][1]
        res = 0
        for i in range(1,len(intervals)):
            start = intervals[i][0]
            end = intervals[i][1]
            if start >= first_end:
                first_end = end
            else:
                res+=1
        return res
```     

2. Thoughts

(1). Notice the extraodinary similarity of this problem to 452.  Minimum Number of Arrows to Burst Balloons.

These two problems are kind of 'reversed'
