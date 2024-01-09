# Selection Sort

<img src="https://upload.wikimedia.org/wikipedia/commons/3/3e/Sorting_selection_sort_anim.gif" align="center">

Selection sort is a simple and efficient sorting algorithm that works by repeatedly selecting the smallest (or largest) element from the unsorted portion of the list and moving it to the sorted portion of the list. The algorithm maintains two sublists in a given array.

1. The sublist which is already sorted.
2. Remaining sublist which is unsorted.

In every iteration of selection sort, the minimum element from the unsorted sublist is picked and moved to the sorted sublist.

## Description

The algorithm works as follows:

1. Initialize a iterator $i$ to $0$.
2. Initialize a variable $min$ to $i$.
3. Iterate over the list from $i+1$ to $n-1$.
4. If $L[min] > L[j]$, set $min$ to $j$.
5. Swap $L[i]$ and $L[min]$.
6. Increment $i$ by $1$.

## Worked Example

Here is a worked example of the algorithm:

## Trace Table

## Psuedocode

<!-- ```{prf:algorithm} Bubble Sort Algorithm
:label: my-algorithm

**Inputs** Given a list of numbers $L$ of length $n$ 

**Output** A sorted list of numbers $L$ of length $n$

$n$ $\leftarrow$ length(L)

For $i$ from $0$ to $n-1$: \
    \
    $min$ $\leftarrow$ $i$ \
    \
    For $j$ from $i+1$ to $n-1$: \
    \
        If $L[min] > L[j]$: \
    \
            $min$ $\leftarrow$ $j$ \
    \
        end If \
    \
    Swap $L[i]$ and $L[min]$ \
    \
end For

``` -->


## Implementation

```python
def selectionSort(arr):
    n = len(arr)
     
    # Traverse through all array elements
    for i in range(n):
         
        # Find the minimum element in remaining
        # unsorted array
        min_idx = i
        for j in range(i+1, n):
            if arr[min_idx] > arr[j]:
                min_idx = j
                 
        # Swap the found minimum element with
        # the first element        
        arr[i], arr[min_idx] = arr[min_idx], arr[i]
```

## Complexity

The time complexity of selection sort is $O(n^2)$ in all cases. The space complexity is $O(1)$.

### Time Complexity

Time Complexity of selection sort is $O(n^2)$ in all cases.

In the best case, the list is already sorted. In this case, the algorithm will perform $n$ comparisons and $0$ swaps. Thus, the time complexity is $O(n)$.

In the worst case, the list is sorted in reverse order. In this case, the algorithm will perform $n$ comparisons and $n$ swaps. Thus, the time complexity is $O(n^2)$.

In the average case, the list is not sorted. In this case, the algorithm will perform $n$ comparisons and $n/2$ swaps. Thus, the time complexity is $O(n^2)$.

### Space Complexity

Space Complexity of selection sort is $O(1)$. This is because the algorithm sorts the list in-place.

## Visualization

```{figure} https://he-s3.s3.amazonaws.com/media/uploads/2888f5b.png
---
height: 300px
name: selection-sort
---
Selection Sort
```

## Animation 

```{figure} https://miro.medium.com/v2/resize:fit:1144/1*5WXRN62ddiM_Gcf4GDdCZg.gif
---
height: 300px
name: selection-sort
---
Selection Sort
```

## Advantages of Selection Sort

1. Selection sort is simple to implement.
2. Selection sort is efficient for small data sets.
3. Selection sort is an in-place sorting algorithm. Thus, it does not require any extra space.
4. Selection sort is a stable sorting algorithm.

## Disadvantages of Selection Sort

1. Selection sort is inefficient for large data sets.
2. Selection sort is not a practical sorting algorithm when compared to other sorting algorithms like quick sort, merge sort, etc.




