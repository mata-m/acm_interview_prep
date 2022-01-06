---
order: 999
---
# Binary Search

Binary Search problems can actually be generalized to **"Find the minimum/maximum value for which a condition is satisfied."**

## Template

This template is pretty much all you need to memorize for interview problems that can be reduced to Binary Search.

The most important part to figure out is the search space and you'll notice that unlike in regular Binary Search, the search space doesn't need to be given to you in the form of an array.
An example of this can be seen [here](https://leetcode.com/problems/capacity-to-ship-packages-within-d-days/) where you are given an array of weights but the actual search space is possible truck capacities.  

Swap "right = mid - 1" & "left = mid + 1" in the **first** template below to instead search
for the **maximum** value for which a condition is satisfied.

```python # Find the **minimum** value for which a condition is satisfied
def binarySearch(nums, target, isConditionTrue):
    left, right = 0, len(nums) - 1 # Valid search space
    boundaryIdx = -1 # Last idx for which condition was satisfied
    while left <= right:
        mid = (left + right) // 2
        if isConditionTrue(mid, target): # Cond must be true of target & 
                                         # all values to right of target
            boundaryIdx = mid
            right = mid - 1 # Look to the left 
        else: # Disregard this value
            left = mid + 1 # Look to the right
    return boundaryIdx # Don't forget case where target not found, etc..
```

```python #  Similar template from [popular LC post](https://leetcode.com/discuss/general-discussion/786126/python-powerful-ultimate-binary-search-template-solved-many-problems) 
def binary_search(array) -> int:
    def condition(value) -> bool:
        pass

    left, right = min(search_space), max(search_space) # could be [0, n], [1, n] etc. Depends on problem
    while left < right:
        mid = left + (right - left) // 2
        if condition(mid):
            right = mid
        else:
            left = mid + 1
    return left
```
## Worked Example
Insert animation here



