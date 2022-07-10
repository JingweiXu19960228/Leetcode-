1. Wrong code


class Solution:
    def minimumTotal(self, triangle: List[List[int]]) -> int:
        
        def helper(n,triangle:List[List[int]]) -> int:     # Return the minimum total of first n layers
            if n==0:
                return triangle[0][0], 0
            elif n==1:
                if triangle[1][0] > triangle[1][1]:
                    return triangle[0][0] + triangle[1][1], 1
                else:
                    return triangle[0][0] + triangle[1][0], 0
                
            else:
                minimum, index = helper(n-1,triangle)
                if triangle[n][index] > triangle[n][index+1]:
                    return minimum + triangle[n][index+1],index+1
                else:
                    return minimum + triangle[n][index],index
            
        height =  len(triangle[-1])
       
        return helper(height-1,triangle)[0]
                
           
        
