1. Right code
```
class Solution:
    def findRedundantConnection(self, edges: List[List[int]]) -> List[int]:
        
        def dfs(node1,node2,graph,visited):
            if node1 == node2:
                return True
            if not node1 in visited:
                visited.add(node1)                
                stat = False
                for neighbor in graph[node1]:
                    stat = stat or dfs(neighbor,node2,graph,visited)
                return stat
        
        graph = collections.defaultdict(set)
        
        for u,v in edges:
            if u in graph and v in graph and dfs(u,v,graph,set()):
                return [u,v]
            
            graph[v].add(u)
            graph[u].add(v)
```
            
        
2. Thoughts

(1). Notice that in the main part of the code (line 17-22), the 'if' statement is executed before the vertex is added
This sequence is important!

