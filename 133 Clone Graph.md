1. Right code

class Solution:
    def __init__(self) -> None:
        self.visited = {}

    def cloneGraph(self, node: 'Node') -> 'Node':
        if not node:
            return node
        
        if node in self.visited:
            return self.visited[node]
         
        clone_node = Node(node.val,[])

        self.visited[node] = clone_node

        clone_node.neighbors = [self.cloneGraph(n) for n in node.neighbors]

        return clone_node
        
 2. Thought
 (1) Understand the purpose of line 11-12
 
