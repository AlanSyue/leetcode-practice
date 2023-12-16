# Two Sum
## Description
Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

You can return the answer in any order.

 

Example 1:

Input: nums = [2,7,11,15], target = 9
Output: [0,1]
Explanation: Because nums[0] + nums[1] == 9, we return [0, 1].
Example 2:

Input: nums = [3,2,4], target = 6
Output: [1,2]
Example 3:

Input: nums = [3,3], target = 6
Output: [0,1]
 

Constraints:

2 <= nums.length <= 104
-109 <= nums[i] <= 109
-109 <= target <= 109
Only one valid answer exists.
 

Follow-up: Can you come up with an algorithm that is less than O(n2) time complexity?

## Solution
1. Start
2. Initialize an empty hashmap
3. Iterate over all numbers in the array
- For each number calculate its target number, for example, if 2 then target is 7
- Store the current iteration's number and its index in a hashmap
- Check if the target number needed is in the hashmap - If yes, go to step 4. If no, continue with the next number (step 3)
4. Return the index of the target number in the hashmap and the index of the current number from the iteration
5. End

```python
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        nums_mapping = {}

        index = 0
        for num in nums:
            matched_num = target - num

            if matched_num in nums_mapping:
                matched_num_index = nums_mapping[matched_num]
                return [matched_num_index, index]

            nums_mapping[num] = index
            index += 1 
```
