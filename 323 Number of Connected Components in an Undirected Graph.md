1. Right code

    ```
    class Solution:
    def countComponents(self, n: int, edges: List[List[int]]) -> int:
        def dfs(n):      
            for m in pairs[n]:
                if m not in visited:
                    visited.add(m)
                    dfs(m)
                    
        pairs = defaultdict(set)
       
        for u,v in edges:
            pairs[u].add(v)
            pairs[v].add(u)

        count = 0
        visited = set()
        for i in range(n):
            if i not in visited:
                dfs(i)
                count+=1

        return count
        
  ```      
        
  2. Thought
  (1).  The function dfs(n) would add all the nodes (that are connected to n) to 'visited'    
            
