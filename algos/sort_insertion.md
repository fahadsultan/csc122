
<img align="right" src="https://upload.wikimedia.org/wikipedia/commons/2/24/Sorting_insertion_sort_anim.gif">

# Insertion Sort

Insertion sort is a simple sorting algorithm that works the way we sort playing cards in our hands. 

## Steps 

The algorithm works as follows:

1. Initialize a iterator $i$ to $1$.

2. Initialize a variable $key$ to $L[i]$.

3. Iterate over the list from $i-1$ to $0$.

4. If $L[j] > key$, set $L[j+1]$ to $L[j]$.

5. Set $L[j+1]$ to $key$.

6. Increment $i$ by $1$.

## Worked Example

Here is a worked example of the algorithm:

## Trace Table

## Psuedocode
<!-- 
```{prf:algorithm} Insertion Sort Algorithm
:label: my-algorithm

**Inputs** Given a list of numbers $L$ of length $n$

**Output** A sorted list of numbers $L$ of length $n$

$n$ $\leftarrow$ length(L)

For $i$ from $1$ to $n-1$: \
    \
    $key$ $\leftarrow$ $L[i]$ \
    \
    $j$ $\leftarrow$ $i-1$ \
    \
    While $j \geq 0$ and $L[j] > key$: \
    \
        $L[j+1]$ $\leftarrow$ $L[j]$ \
    \
        $j$ $\leftarrow$ $j-1$ \
    \
    end While \
    \
    $L[j+1]$ $\leftarrow$ $key$ \
    \
end For

``` -->

## Implementation

```python

# Python program for implementation of Insertion Sort

# Function to do insertion sort
def insertionSort(arr):

    # Traverse through 1 to len(arr)
    for i in range(1, len(arr)):

        key = arr[i]

        # Move elements of arr[0..i-1], that are
        # greater than key, to one position ahead
        # of their current position
        j = i-1
        while j >=0 and key < arr[j] :
                arr[j+1] = arr[j]
                j -= 1
        arr[j+1] = key
```

## Complexity

The complexity of the algorithm is $O(n^2)$.

### Time Complexity

Time Complexity of insertion sort is $O(n^2)$ in all cases.

### Space Complexity

Space Complexity of insertion sort is $O(1)$ in all cases.

## Animation

## Advantages

1. Simple implementation
2. Efficient for small data sets
3. Adaptive, i.e., efficient for data sets that are already substantially sorted: the time complexity is $O(nk)$ when each element in the input is no more than $k$ places away from its sorted position
4. Stable; i.e., does not change the relative order of elements with equal keys

## Disadvantages

1. More efficient algorithms such as quicksort, heapsort, or merge sort are used by the library function `sort()`
2. Insertion sort is very slow for large data sets
3. Insertion sort is not a practical sorting algorithm when $n$ is large
