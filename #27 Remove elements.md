
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
* Remove the specified elements, keep the remaining n-m element in place   (a
* Return the number of elements that are not removed (i.e., n-m).  (b
## The inefficiency of the brute force solution:  
The time complexity is $o(n^2)$
many 'unnecessary' elements are updated in each iteration

## The insight for a better solution


# 2. Optimized solution

