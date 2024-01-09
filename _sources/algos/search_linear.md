# Linear Search

## Problem Statement
Given an array of integers, find the index of a given element in the array.

<img src="../assets/sequential_search.gif">

## Solution
```python
list = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
target = 5

def linear_search(list, target):
    """
    Returns the index position of the target if found, else returns None
    """
    for i in range(0, len(list)):
        if list[i] == target:
            return i
    return None

print(linear_search(list, target))
```

## Analysis

### Time Complexity

The time complexity of the above algorithm is `O(n)` since in the worst case we have to iterate over the entire list to find the target.

### Space Complexity

The space complexity of the above algorithm is `O(1)` since we are not using any extra space.

## References

- [Wikipedia](https://en.wikipedia.org/wiki/Linear_search)