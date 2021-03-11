# Two Pointers
#### LC26. Remove Duplicates from Sorted Array
Given a sorted array nums, remove the duplicates in-place such that each element appears only once and returns the new length.

Do not allocate extra space for another array, you must do this by modifying the input array in-place with O(1) extra memory.

- Pointer 1: `lastNondup` track the index of the last non-duplicate number

- Pointer 2: `i` iterate through each number 

- Remember to convert index `lastNondup` to the length

```python
def removeDuplicates(self, nums):
    """
    :type nums: List[int]
    :rtype: int
    """
    lastNondup = 0
    if len(nums) <=1:
        return len(nums)
    else:         
        for i in range(1,len(nums)):
            if nums[i] != nums[lastNondup]:
                lastNondup += 1
                nums[lastNondup] = nums[i]
        lastNondup +=1 #convert index to length     
        return lastNondup
```
