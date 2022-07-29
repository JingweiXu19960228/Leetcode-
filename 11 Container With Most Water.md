1. Wrong code

class Solution:
    def maxArea(self, height: List[int]) -> int:
        i = 0
        j = len(height)-1
        area = 0
        
        while(i<j):
            area = max(area, (j-i)*min(height[i],height[j]))
            
            if height[i+1] > height[i]:
                i+=1
            if height[j-1] > height[j]:
                j-=1

            
 2. Right code

