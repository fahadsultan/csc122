# Bubble Sort

<img src="https://upload.wikimedia.org/wikipedia/commons/5/54/Sorting_bubblesort_anim.gif">

Bubble sort is a simple sorting algorithm that repeatedly steps through the list, compares adjacent elements and swaps them if they are in the wrong order. The pass through the list is repeated until the list is sorted. The algorithm, which is a comparison sort, is named for the way smaller or larger elements "bubble" to the top of the list. 

Although the algorithm is simple, it is too slow and impractical for most problems. It can be practical if the input is usually in sort order but may occasionally have some out-of-order elements nearly in position.

## Steps 

In Bubble Sort algorithm, 

1. traverse from left and compare adjacent elements and the higher one is placed at right side. 
2.  In this way, the largest element is moved to the rightmost end at first. 
3. This process is then continued to find the second largest and place it and so on until the data is sorted.

## Psuedocode

```{prf:algorithm} Bubble Sort Algorithm
:label: my-algorithm

**Inputs** Given a list of numbers $L$ of length $n$ 

**Output** A sorted list of numbers $L$ of length $n$

$n$ $\leftarrow$ length(L)

For $i$ from $0$ to $n-1$: \
    \
    For $j$ from $0$ to $n-i-1$: \
    \
        If $L[j] > L[j+1]$: \
    \
            Swap $L[j]$ and $L[j+1]$

        end If

    end For

end For

```

## Description 

The algorithm works as follows:

2. Initialize a iterator $i$ to $0$.
3. Compare $L[i]$ and $L[i+1]$. If $L[i] > L[i+1]$, swap them.
4. Increment $i$ by $1$.


## Worked Example 

Here is a worked example of the algorithm:

## Trace Table 

## Code 

```python
def bubbleSort(arr):
    n = len(arr)
     
    # Traverse through all array elements
    for i in range(n):
        swapped = False
 
        # Last i elements are already in place
        for j in range(0, n-i-1):
 
            # Traverse the array from 0 to n-i-1
            # Swap if the element found is greater
            # than the next element
            if arr[j] > arr[j+1]:
                arr[j], arr[j+1] = arr[j+1], arr[j]
                swapped = True
        
        if (swapped == False):
            break
```

## Animation 

## Analysis 

The analysis of bubble sort algorithm can be done in two parts:

1. Time Complexity
2. Space Complexity


### Time Complexity

Time Complexity of bubble sort is $O(n^2)$ in worst and average case. In best case, it is $O(n)$ when the list is already sorted.

The best case occurs when the array is already sorted. So the number of comparisons required is N-1 and the number of swaps required = 0. Hence the best case complexity is O(N).

The worst-case condition for bubble sort occurs when elements of the array are arranged in decreasing order. In the worst case, the total number of iterations or passes required to sort a given array is (N-1). where ‘N’ is the number of elements present in the array.

In worst case, Total number of swaps = Total number of comparison
Total number of comparison (Worst case) = N(N-1)/2
Total number of swaps (Worst case) = N(N-1)/2

So worst case time complexity is O(N2) as N2 is the highest order term.

**Average Case Time Complexity**: The number of comparisons is constant in Bubble Sort. So in average case, there are O(N2) comparisons. This is because irrespective of the arrangement of elements, the number of comparisons C(N) is same.

For the number of swaps, consider the following points:

If an element is in index I1 but it should be in index I2, then it will take a minimum of (I2-I1) swaps to bring the element to the correct position.
Consider an element E is at a distance of I3 from its position in sorted array. Then the maximum value of I3 will be (N-1) for the edge elements and N/2 for the elements at the middle.
The sum of maximum difference in position across all elements will be:

(N – 1) + (N – 3) + (N – 5) . . . + 0 + . . . + (N-3) + (N-1)
= N x (N – 2) x (1 + 3 + 5 + … + N/2)
= N2 – (2 x N2 / 4)
= N2 – N2 / 2
= N2 / 2

Therefore, in average case the number of comparisons is O(N2)

### Space Complexity

Space Complexity of bubble sort is $O(1)$ because only a single additional memory space is required i.e. for temp variable.


The algorithm can be expressed as:

<img align="center" src="https://upload.wikimedia.org/wikipedia/commons/c/c8/Bubble-sort-example-300px.gif?20131109191607">

<img align="center" src="https://miro.medium.com/v2/resize:fit:679/0*nh6F_qERbgD3xmV-.gif">

<img align="center" src="https://miro.medium.com/v2/resize:fit:776/format:webp/1*7QsZkfrRGhAu5yxxeDdzsA.png">


## Advantages of Bubble Sort:

* Bubble sort is easy to understand and implement.
* It does not require any additional memory space.
* It is a stable sorting algorithm, meaning that elements with the same key value maintain their relative order in the sorted output.

## Disadvantages of Bubble Sort:

* Bubble sort has a time complexity of O(N2) which makes it very slow for large data sets.
* Bubble sort is a comparison-based sorting algorithm, which means that it requires a comparison operator to determine the relative order of elements in the input data set. * It can limit the efficiency of the algorithm in certain cases.