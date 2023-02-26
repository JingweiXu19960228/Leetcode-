1. Right code

```
class Solution:
    def findItinerary(self, tickets: List[List[str]]) -> List[str]:

        def dfs(dep):
            arr = path[dep]
            while arr:
                dfs(arr.pop())
            res.append(dep)

        tickets.sort(key = lambda x:x[1], reverse = True)
        
        path = defaultdict(list)
        
        for i,j in tickets:
            path[i].append(j)
        res = []
        dfs('JFK')
        return res[::-1]
 ```  
       
       
 2. Thought
 
 (1). I cannot understand how the dfs function work  . Why the node 'dep' is added in the end ?
 
 (2). It is hard to understand why tickets are soreted in reverse order
 
 
