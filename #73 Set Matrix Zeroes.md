    
    #1 WRONG CODE (1st attempt):
    ```
    def setZeroes(self, matrix: List[List[int]]) -> None:
        """
        Do not return anything, modify matrix in-place instead.
        """
        height=len(matrix)
        width=len(matrix[0])
        d_row=[0]*height
        d_column=[0]*width
        
        for i in range(height):
            for j in range(width):
                element=matrix[i][j]
                if element==0 and d_row[i]==0 and d_column[j]==0:
                    for k in range(len(matrix)):
                        matrix[k][j]=0
                        matrix[i][k]=0
                        d_row[i]=1
                        d_column[j]=1
    ```
                        
