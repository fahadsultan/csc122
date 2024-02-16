


# Practice Exam for Data Structures and Algorithms 

## Problem 0 

For the figure above, match letter with one of the following set of functions: 

{ quadratic O(n^2), exponential O(2^n), logarithmic O(log n), linear O(n), constant (1), cubic O(n^3) }

A: 
B: 
C: 
D: 
E:
F: 

## Problem 1

For the following lines of code, what is the time and space complexity?

1.1. 

```python
def foo(n):
    s = 0
    i = 0 
    while i < n:
        s = s + i
        i = i + 1
    return s
```

1.2.

```python

def baz(n):
    i = n 
    s = 0 
    while i > 1: 
        s = s + n
        i = i / 2
    return s
```

1.3.

```python

def bar(n):
    i = 1 
    s = 0
    while i < n: 
        s = s + 1
        i = i * 2
    return s
```

1.4. 

```python

def qux(data):
    i = 0 
    j = 0 
    while i != j: 
        data[i], data[j] = data[j], data[i]
        i = i + 1
        j = j - 1
    return data
```

1.5. 

```python
def create_range(n):
    data = []
    i = 0
    while i < n:
        data.append(i)
        i = i + 1
    return data
```

1.6. 

```python

def read(data, loc):
    return data[loc]
```

1.7. 

```python

def update(data, value, new_value):
    i = 0
    while i < len(data):
        if data[i] == value:
            data[i] = new_value
        i = i + 1
    return data
```

1.6. 

```python

def insert(data, loc, value):
    new_data = []
    i = 0
    while i < loc:
        new_data.append(data[i])
        i = i + 1

    i = len(data) - 1
    while i > 0 and data[i] < data[i - 1]:
        data[i], data[i - 1] = data[i - 1], data[i]
        i = i - 1
    return data
```

1.7. 

```python

def remove(data, value):
    i = 0
    while i < len(data):
        if data[i] == value:
            data[i], data[len(data) - 1] = data[len(data) - 1], data[i]
            data.pop()
        else:
            i = i + 1
    return data
```

## Problem 2

Write the most efficient function to find query in a descending list of numbers. The function should return the index of the query if it is in the list and -1 if it is not.

Solution: 

```python
def find_query(data, query):
    left = 0
    right = len(data) - 1
    while left <= right:
        mid = (left + right) // 2
        if data[mid] == query:
            return mid
        elif data[mid] < query:
            right = mid - 1
        else:
            left = mid + 1
    return -1
```

What is the time and space complexity of your function?


## Problem 3 

Write the most efficient function to find the maximum value in an ordered list of numbers.

What is the time and space complexity of your function?

## Problem 4 

Write a function that takes in a list of numbers and reverses the list. The function should be O(n) in time and O(1) in space.

## Problem 5

Write a function that takes in a list of numbers and returns the maximum difference between any two numbers in the list. The function should be O(n) in time and O(1) in space. 

For example, the maximum difference in [3, 1, 5, 2, 4]  is 4 since 5 - 1 = 4.

Similarly, the maximum difference in [1, 1, 1, 2, 2, 2] is 1 since 2 - 1 = 1.

Another example, the maximum difference in [-1, -20, -10] is 19 since -1 - (-20) = 19.

```python

def find_max

def max_difference(data):
    if len(data) < 2:
        return 0
    min_value = data[0]
    max_difference = 0
    for i in range(1, len(data)):
        max_difference = max(max_difference, data[i] - min_value)
        min_value = min(min_value, data[i])
    return max_difference

assert max_difference([3, 1, 5, 2, 4]) == 4, "Test case 1 failed"
assert max_difference([1, 1, 1, 2, 2, 2]) == 1, "Test case 2 failed"
assert max_difference([1, 1, 1, 1, 1, 1]) == 0, "Test case 3 failed"
assert max_difference([99, 99, 0, 0]) == 99, "Test case 4 failed"
assert max_difference([1]) == 0, "Test case 5 failed"
assert max_difference([-1, -20, -10]) == 19, "Test case 6 failed"
```