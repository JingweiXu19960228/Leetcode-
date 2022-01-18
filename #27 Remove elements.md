
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
* Remove specified elements, keep the left n-m element in place
* Return the number of elements that are not removed
## The inefficiency of the brute force solution:  
many 'unnecessary' elements are updated in each iteration

## The insight for a better solution

2. Optimized solution

