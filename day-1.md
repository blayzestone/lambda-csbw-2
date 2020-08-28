Problem 1:
https://leetcode.com/problems/contains-duplicate/

Solution:
`
class Solution(object):
    def containsDuplicate(self, nums):        
        # Create a store for visited values in the array
        visited = set()
        
        # loop over the numbers in the array
        for num in nums:
            # if the number exists in the visited store, return True
            if num in visited:
                return True
            # else, add the number to the visited store
            else:
                visited.add(num)
                
        # Return false if no duplicate numbers were found
        return False
`
Problem 2:
https://leetcode.com/problems/add-two-numbers/

Solution:
`
class Solution(object):
    def addTwoNumbers(self, l1, l2):
        
        overflow_digit = 0
        head = ListNode(l1.val + l2.val)
        cur_node = head
        
        while l1.next is not None or l2.next is not None:
            l1 = l1.next
            l2 = l2.next
            
            if l1 is None:
                l1 = ListNode(0)
            elif l2 is None:
                l2 = ListNode(0)
            
            cur_node.next = ListNode(l1.val + l2.val)  
            cur_node = cur_node.next
            
        cur_node = head
        
        while cur_node is not None:
            
            if cur_node.val > 9:
                val = str(cur_node.val)
                overflow_digit = int(val[0])
                cur_node.val = int(val[1])
                
                if cur_node.next is None:
                    cur_node.next = ListNode(overflow_digit)
                else:
                    cur_node.next.val += overflow_digit
                
                
            cur_node = cur_node.next
                
        return head
`