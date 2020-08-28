Problem 1:
https://leetcode.com/problems/merge-two-sorted-lists/

Solution:
`
class Solution:
    def mergeTwoLists(self, l1: ListNode, l2: ListNode) -> ListNode:
        merged_values = []
        head = ListNode(0)
        cur_node = head
        
        if l1 is None:
            return l2
        elif l2 is None:
            return l1
        
        while l1 is not None or l2 is not None:
            if l1 is not None:
                merged_values.append(l1.val)
                l1 = l1.next
                
            if l2 is not None:
                merged_values.append(l2.val)
                l2 = l2.next
            
        merged_values.sort()
        
        for val in merged_values:
            cur_node.next = ListNode(val)
            cur_node = cur_node.next
            
        return head.next
`