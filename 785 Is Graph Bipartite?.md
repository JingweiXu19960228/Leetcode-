1. Right code
```
class Solution:
    def isBipartite(self, graph: List[List[int]]) -> bool:
        def dfs(node,c):
            color[node] = c
            for neighbor in graph[node]:
                if color[neighbor] == c:
                    return False
                if color[neighbor] == 0 and not dfs(neighbor,-c):
                    return False
            return True
        
        
        
        color = [0]*len(graph)
        
        for i in range(len(graph)):
            if color[i]==0:   
                if not dfs(i,1):
                    return False
        return True
```

2. Thoughts
3. 
(1). The dfs function not only return True or False, it also modify the value of the 'color' array (i.e, the process of coloring)

(). Notice that there are two 'if' statement in the dfs function, think about why we need both of them!
