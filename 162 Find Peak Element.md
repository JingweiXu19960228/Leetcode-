1. Right code

class Solution:
    def findPeakElement(self, nums: List[int]) -> int:       
        left = 0
        right =len(nums)-1
        
        while left<right:
            mid = left + (right-left)//2
            
            if nums[mid]>nums[mid+1]:
                right = mid
                
            else:
                left = mid+1
                
        return left
    
    
 2. Thought
 (1). The problem is equivalent to 'finding the first element in the array so that it is larger than its next'
 We can prove by contridiction:
 If one element satisifies this property, but is not peak, then it is smaller than either its previous or next values,
 but it is larger to its next according to the property, so it has to be samller than its previous. If so, then this element
 cannot be the 1st element that... its previous value would be!
