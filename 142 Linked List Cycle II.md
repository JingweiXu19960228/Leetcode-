1. Wrong code:

```
class Solution:
    def detectCycle(self, head: Optional[ListNode]) -> Optional[ListNode]:
        
        slow, fast = head, head
        
        while (slow!=fast) and fast.next:
            slow = slow.next
            fast = fast.next
            
        if not fast.next:
            return None
        
        slow = head
        
        while (slow!=fast):
            slow = slow.next
            fast = fast.next
            
        return fast
```

2. Thought

(1). In line 8, the condition for while loop is NOT correct, and in the right code, if slow == fast, the loop should break immediately 
 (line 41 in the right code)
 
(2). I don't know why the while loop is not right. Maybe just remember

(3). I also don't understand why we also need 'while fast ' (line 41)

4. Right code:
```
class Solution:
    def detectCycle(self, head: Optional[ListNode]) -> Optional[ListNode]:
        
        slow, fast = head, head
        
        while fast and fast.next:
            slow = slow.next
            fast = fast.next.next
            if slow==fast:
                break
            
        if not fast or not fast.next:
            return None
        
        slow = head
        
        while (slow!=fast):
            slow = slow.next
            fast = fast.next
            
        return fast
  ```      
