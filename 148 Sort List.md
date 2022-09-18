    1. Right code


    ```
    def sortList(self, head: Optional[ListNode]) -> Optional[ListNode]:
        def merge(list1,list2):
            dummy_head = tail = ListNode()
            while(list1 and list2):
                if list1.val < list2.val:
                    tail.next = list1
                    list1 = list1.next
                    
                else:
                    tail.next = list2
                    list2 = list2.next
                
                tail = tail.next
            tail.next = list1 or list2    
            return dummy_head.next
        
        def sort(head):
            if not head or not head.next:
                return head
            pre, slow, fast = None, head, head
            
            while fast and fast.next:
                pre, slow, fast = slow, slow.next, fast.next.next
                
            pre.next = None    
            l1 = self.sort(head)
            l2 = self.sort(slow)
            return self.merge(l1,l2)
       
        ```
        
        2. Thoughts:
        (1).  Line 29 is important. So that the last half of node 'head' is cleared. Notice that it would be wrong if 
        'slow.next = None', because in Line 27, we have 'slow = slow.next'
        
