---
order: 999
---
# Binary Search

Binary Search problems can actually be generalized to **"Find the minimum/maximum value for which a condition is satisfied."**

## Template
Swap "right = mid - 1" & "left = mid + 1" in the template below to instead search
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
    return boundaryIdx
```
## Worked Example
Insert animation here



