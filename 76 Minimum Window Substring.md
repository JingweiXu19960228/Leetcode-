1. Right code
```
class Solution:
    def minWindow(self, s: str, t: str) -> str:
        count = Counter(t)
        Required = len(t)
        bestLeft = -1
        
        minLength = len(s)
        
        l = 0
        for r,c in enumerate(s):
            count[c]-=1
            if count[c]>=0:
                Required-=1
            while (Required==0):
                if r-l+1 <= minLength:
                    bestLeft = l
                    minLength = r-l+1
                count[s[l]]+=1
                if count[s[l]]>0:
                    Required+=1
                l+=1
        
        if bestLeft==-1:
            return ""
        else:
            return s[bestLeft:bestLeft+minLength]
                    

```



2. Thoughts

(a). 'Required' is the required number of variables that still need to be added in the sliding window so that it is a substring
So when 'Required'=0, the current sliding window is good

(b). The way to update 'Required' is very clever (line 14-15, 21-22). Think abut why they are correct
For line 14-15, the if statement would NOT be executed when the current element (c) is NOT part of t
For line 21-22, the if statement would be executed when, if the current element is removed, the sliding window would NOT be a substring.
Then the while loop would be quited.


(c). line 17-19 is for updating the minimum and corresponding location. Be careful about the boundary (r-l+1 rather than r-l)

(d). The purpose of the while loop is to push the left boundary (l) rightward
