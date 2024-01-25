
<img src="https://upload.wikimedia.org/wikipedia/commons/3/3e/Sorting_selection_sort_anim.gif" align="right" width="25%" >

# Selection Sort

**Selection sort** is a simple decrease and conquer sorting algorithm that works by maintaining two sublists in a given array:

1. The sublist which is already sorted.
2. Remaining sublist which is unsorted.

<img width="23%" align="right" src="https://upload.wikimedia.org/wikipedia/commons/b/b0/Selection_sort_animation.gif">

The algorithm iteratively _"selects"_ the smallest (for ascending order) element from the unsorted sublist and appends it to the end of the sorted sublist. This process continues until the unsorted sublist is empty. 

Note that the algorithm does not require any extra space and is thus an in-place sorting algorithm. The two sublists are maintained by a single variables tracking the first element of the unsorted sublist. Everything before this variable is sorted and everything after it is unsorted.

```{figure} https://miro.medium.com/v2/resize:fit:1102/1*H2bCd6eoIONJIUnG5Jm9sQ.gif
---
width: 50%
name: selection-sort
---
Selection Sort iteratively selects the smallest element from the unsorted sublist and appends it to the end of the sorted sublist. 
```

Selection sort _"conquers"_ the sorting problem by _"decreasing"_ the size of the unsorted sublist by one in each iteration.


## Algorithm

The selection sort algorithm, conceptually in broad steps, works as follows:

1. Initialize a iterator $i$ to $0$.
2. Identify the smallest element in the unsorted sublist (from $i$ to $n-1$).
3. Swap the smallest element with the element at index $i$.
4. Increment $i$ by $1$.
5. Repeat steps 2-4 until $i$ is equal to $n-1$.

<center><img width="70%" src="https://miro.medium.com/v2/resize:fit:1144/1*5WXRN62ddiM_Gcf4GDdCZg.gif"></center>

<!-- 
```{figure} 
---
width: 75%
name: selection-sort
---
Selection Sort
``` 
-->

## Psuedocode

```{prf:algorithm} Selection Sort Algorithm
:label: my-algorithm

**Inputs** Given a list of numbers $L$ of length $n$

**Output** A sorted list of numbers $L$ of length $n$

<img width="60%" align="right" src="https://he-s3.s3.amazonaws.com/media/uploads/2888f5b.png">

For $i$ from $0$ to $n-1$: \
&emsp; $min$ $\leftarrow$ $i$ \
&emsp; For $j$ from $i+1$ to $n-1$: \
&emsp; &emsp; If $L[min] > L[j]$: \
&emsp; &emsp; &emsp; $min$ $\leftarrow$ $j$ \
&emsp; &emsp; end If \
&emsp; end For \
&emsp; Swap $L[i]$ and $L[min]$ \
end For
```

## Analysis

Time Complexity of selection sort is $O(n^2)$ in all cases.

In the worst case, the list is sorted in reverse order. In this case, the algorithm will perform $n$ comparisons and $n$ swaps. Thus, the time complexity is $O(n^2)$.

In the best case, the list is already sorted. In this case, the algorithm still performs $n^2$ comparisons but does $0$ swaps. Thus, the time complexity is $O(n^2)$.

In the average case, the list is not sorted. In this case, the algorithm will perform $n$ comparisons and $n/2$ swaps. Thus, the time complexity is $O(n^2)$.

Space Complexity of selection sort is $O(1)$. This is because the algorithm sorts the list in-place.

