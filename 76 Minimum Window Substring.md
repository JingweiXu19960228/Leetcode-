1. Right code
```


```



2. Thoughts

(a). 'Required' is the required number of variables that still need to be added in the sliding window so that it is a substring
So when 'Required'=0, the current sliding window is good

(b). The way to update 'Required' is very clever (line 11-12, 18-19). Think abut why they are correct
For line 11-12, the if statement would NOT be executed when the current element (c) is NOT part of t
For line 18-19, the if statement would be executed when, if the current element is removed, the sliding window would NOT be a substring.
Then the while loop would be quited.


(c). line 14-16 is for updating the minimum and corresponding location. Be careful about the boundary (r-l+1 rather than r-l)

(d). The purpose of the while loop is to push the left boundary (l) rightward
