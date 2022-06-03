
#  1. Solution
```
    def firstBadVersion(self, n: int) -> int:
        start=1
        end=n

        
        while end>=start:     
            mid=start+ int((end-start)/2) 
            if isBadVersion(mid):
                end=mid-1
            else:
                start=mid+1
               
        return start
```


#  2. Thought


The function returns 'start', which is the next element of mid (and mid is the last version that is good)

