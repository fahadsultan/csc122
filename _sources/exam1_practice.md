


# Practice Exam for Data Structures and Algorithms 

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

def insert(data, value):
    data.append(value)
    i = len(data) - 1
    while i > 0 and data[i] < data[i - 1]:
        data[i], data[i - 1] = data[i - 1], data[i]
        i = i - 1
    return data
```

1.6. 

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

1.8. 

```python
