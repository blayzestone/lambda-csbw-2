problem 1:
https://leetcode.com/problems/find-the-duplicate-number/

solution:
`
class Solution:
    def findDuplicate(self, nums: List[int]) -> int:
        visited = set()
        
        for num in nums:
            if num in visited:
                return num
            else:
                visited.add(num)
                
        return -1
`

problem 2:
https://leetcode.com/problems/search-in-rotated-sorted-array/submissions/

solution:
`
class Solution:
    def search(self, nums: List[int], target: int) -> int:
        for i in range(len(nums)):
            if nums[i] == target:
                return i
            
        return -1
`