1. Wrong code
```
class Solution:
    def canFinish(self, numCourses: int, prerequisites: List[List[int]]) -> bool:
        preMap = collections.defaultdict(list)
        
        for crs, pre in prerequisites:
            preMap[crs].append(pre)
                                      (line 4)
        def dfs(crs):
            visited = set()           (line 3)
            if preMap[crs] == []:
                return True
            if crs in visited:
                return False

            visited.add(crs)
            for pre in preMap[crs]:
                if not dfs(pre):
                    return False
            visited.remove(crs)
            preMap[crs] = []           (line 5)
            return True
        
        # for crs in preMap:           (line 1)
        for crs in range(numCourses):  (line 2)
            if not dfs(crs):
                return False
        return True
 ```       
 2. Thought:
 
 (1). I changed from line 1 to line 2, but still does not work
 
 (2). It turns out that line 3 should be in the position of line 4. But I don't know why (after making this change, the code works)
 
 (3). Line 5 is necessary, otherwise the time limit will be reached 
 
 (4）. Think about some concrete examples, like [[0,1],[1,0]]
 
 (5). Notice the line 'visted.remove(crs)'. This line would be executed only when in the for loop, all the dfs(pre) is True (i.e, all nodes starting from current crs can be finished)
 
 (6).
 
 
 
 
 
