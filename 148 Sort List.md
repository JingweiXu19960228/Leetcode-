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
