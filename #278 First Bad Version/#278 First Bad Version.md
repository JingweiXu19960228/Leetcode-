
#  1. Brute force solution:
```
    def removeElement(self, nums: List[int], val: int) -> int:
        if nums==[]:
            return 0
        else:
            k=0
            i=0
            while (k<len(nums)):
                if nums[i]==val:
                    for j in range(i+1,len(nums)):
                        nums[j-1]=nums[j]
                else:
                    i+=1
                k+=1
            return i
```
The number of elements: n.   The number of the specified elements: m
The code need to do 2 taskes
* Remove the specified elements, keep the remaining n-m element in place   (a)
* Return the number of elements that are not removed (i.e., n-m).  (b)
## The inefficiency of the brute force solution:  
* The time complexity is o(n^2), because there are 2 passes. The 2nd pass is used to update the array when finding specified elements
  That is to say, the array elements updated o(n^2) times, too
* However, we only care about the first n-m elements in the final array, which means that the array only needs to be updated at most n-m times
* The above two observations indicate that many elements re-positioning are unnecessary
  

## The insight for a better solution
* Both task (a) and (b) can be done in o(n) time, so a single pass should work
* Since we need to return the number of remaining elements, it is intuitive to use another index to count the number of remaining elements so far,
  in addition to the iterator itself
* The observation indicates that we can use a two-pointer approach


# 2. Optimized solution

