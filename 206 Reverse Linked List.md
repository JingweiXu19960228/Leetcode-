1. Right code
```
class Solution:
    def reverseList(self, head: Optional[ListNode]) -> Optional[ListNode]:
        
        if not head or not head.next:
            return head
        
        p = head.next
        n = self.reverseList(p)
        
        head.next = None     
        p.next = head
        
        return n
```


2. Thoughts
(1). I cannot understant the line 'p.next = head'. I thought it should be 'n.next = head'
Because n is the reversed list of the rest n-1 node, rather than p. Maybe p is somehow moedified when calling the function 'revsereList'
