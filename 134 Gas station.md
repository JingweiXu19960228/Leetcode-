1. Right code

```
class Solution:
    def canCompleteCircuit(self, gas: List[int], cost: List[int]) -> int:
        l = len(gas)
        start = cur = tot = 0
        
        for i in range(l):
            t = gas[i]-cost[i]
            cur+=t
            tot+=t
            if cur<0:
                cur,start = 0,i+1
            
        if tot<0:
            return -1
        else:
            return start

```


2. Thoughts:
(1). It should be noticed that the two statements  "The route can be finished"  and "tot>=0" is equivalent to each other


(2) Be careful about 'cur' and 'tot'. 'cur' needs to be updated whenever it is smaller than 0. So the final index 'i+1' corresponds to the last i that
cur<0. From i+1 to n, it is obvious that the route can be continued, because for every j in [i+1,N], gas[j]-cost[j]>0, otherwise cur will be updated again
And then from 1 to i, the route can be finished, otherwise tot>=0 will not be satisfied
