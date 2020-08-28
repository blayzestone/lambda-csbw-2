Problem 1:
https://leetcode.com/problems/two-sum/

Solution:
`
class Solution:
    def twoSum(self, nums, target):
        visited = {}
        for i in range(len(nums)):
            needed = target - nums[i]
            
            if nums[i] in visited:
                return [visited[nums[i]], i]
            
            visited[needed] = i
`

Problem 2:
https://leetcode.com/problems/implement-queue-using-stacks/

Solution:
`
class MyQueue(object):

    def __init__(self):
        """
        Initialize your data structure here.
        """
        self.q = []
        

    def push(self, x):
        """
        Push element x to the back of queue.
        :type x: int
        :rtype: None
        """
        self.q.append(x)
        

    def pop(self):
        """
        Removes the element from in front of queue and returns that element.
        :rtype: int
        """
        return self.q.pop(0)
        

    def peek(self):
        """
        Get the front element.
        :rtype: int
        """
        return self.q[0]
        
        

    def empty(self):
        """
        Returns whether the queue is empty.
        :rtype: bool
        """
        if len(self.q) == 0:
            return True
        else:
            return False
`
