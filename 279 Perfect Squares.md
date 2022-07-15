1. Wrong code
2. 
class Solution:
    def numSquares(self, n: int) -> int:
        
        N = int(sqrt(n))
        squares = [i*i for i in range(0,N+1)]
        
        if n in squares:
            return 1
        
        minimum = 1
        
        for i in range(1,N+1):
            if n - squares[i] not in squares:
                minimum = min(minimum, 1 + self.numSquares(n-squares[i]))
            else:
                mini
        return minimum
