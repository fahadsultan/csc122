
<img src="https://upload.wikimedia.org/wikipedia/commons/2/24/Sorting_insertion_sort_anim.gif" align="right" width="25%">

# Insertion Sort

**Insertion sort** is a sorting algorithm that works the way we sort playing cards in our hands. 

The algorithm works by maintaining two sublists in a given array:

1. The sublist which is already sorted.
2. Remaining sublist which is unsorted.

<img width="23%" align="right" src="https://upload.wikimedia.org/wikipedia/commons/2/25/Insertion_sort_animation.gif">

The algorithm iteratively _"inserts"_ the next element from the unsorted sublist into the correct position in the sorted sublist. This process continues until the unsorted sublist is empty.

Similar to selection sort, the algorithm does not require any extra space the two sublists are maintained by a single variables tracking the first element of the unsorted sublist. Everything before this variable is sorted and everything after it is unsorted.


```{figure} https://miro.medium.com/v2/resize:fit:1102/1*qc-KD7DII1K097jnvOWqsg.gif
---
width: 60%
name: selection-sort
---
Insertion Sort is similar to how we sort playing cards in our hands. We iteratively insert the next element from the unsorted sublist into the correct position in the sorted sublist. 
```


## Steps 

The algorithm works as follows:

1. Initialize a iterator $i$ to $1$.

2. Call the element at $i^{th}$ location $key$ i.e. $key \leftarrow L[i]$.

3. Iterate over sublist to the left of $i$ from right to left i.e. iterate over the list from $i-1$ to $0$ using an iterator called $j$. The sublist from $i-1$ to $0$ is the sorted sublist.

4. For all values $L[j] > key$, shift them one place to the right i.e. set $L[j+1]$ to $L[j]$ until $L[j] > key$.

5. Once you find a value $L[j] \leq key$, you've found the correct location of $key$. Set $L[j+1]$ to $key$.

6. Increment $i$ by $1$ and repeat steps 2-5 until $i$ is equal to $n-1$.

``` {figure} https://miro.medium.com/v2/resize:fit:1280/1*jdXtqXw0EQVpqdZZoGnwsQ.gif
---
width: 90%
name: insertion-sort
---
Insertion Sort is similar to how we sort playing cards in our hands. We iteratively insert the next element from the unsorted sublist into the correct position in the sorted sublist. Note that the animation above is sorting in descending order.
```


## Psuedocode

```{prf:algorithm} Insertion Sort Algorithm
:label: my-algorithm


**Inputs** Given a list of numbers $L$ of length $n$

**Output** A sorted list of numbers $L$ of length $n$

<img align="right" width="60%" src="https://he-s3.s3.amazonaws.com/media/uploads/46bfac9.png">

$n$ $\leftarrow$ length(L)

For $i$ from $1$ to $n-1$: \
&emsp; $key$ $\leftarrow$ $L[i]$ \
&emsp; $j$ $\leftarrow$ $i-1$ \
&emsp; While $j \geq 0$ and $L[j] > key$: \
&emsp; &emsp; &emsp; $L[j+1]$ $\leftarrow$ $L[j]$ \
&emsp; &emsp; &emsp; $j$ $\leftarrow$ $j-1$ \
&emsp; end While \
&emsp; $L[j+1]$ $\leftarrow$ $key$ \
end For

``` 


## Analysis

The time complexity of insertion sort depends on the initial order of the elements in the input array. 

In the worst case, the array is sorted in reverse order. In this case, the algorithm will perform $n$ comparisons and $n(n-1)/2$ swaps. Thus, the time complexity is $O(n^2)$.

In the average case, the array is randomly ordered. In this case, the algorithm will perform $n$ comparisons and $n(n-1)/4$ swaps. Thus, the time complexity is $O(n^2)$.

In the best case, the array is already sorted. In this case, the algorithm will perform $n$ comparisons and $0$ swaps. Thus, the time complexity is $O(n)$. Note that the best case of insertion sort is better than the best case of selection sort.

The space complexity of insertion sort is $O(1)$ in all cases as the algorithm does not require any extra space.

## Comparison with Selection Sort

Selection and Insertion sort are similar algorithms with some subtle but key differences. 

### Similarities

They are similar in that they are

* Both decrease and conquer sorting algorithms
* Both maintain two sublists in a given array: 
    * The sublist which is already sorted.
    * Remaining sublist which is unsorted.
* Both have a time complexity of $O(n^2)$
* Both are in-place sorting algorithms 
* The space complexity of both is $O(1)$

### Differences 

They two key difference in that:

1. In selection sort, most of the work done is in "selecting" (finding) the smallest element in the unsorted sublist. 

    <br/>
    
    In insertion sort, most of the work is done in "inserting" the next element from the unsorted sublist into the correct position in the sorted sublist.

```{figure} ../assets/select_vs_insert.png
---
width: 90%
name: select-vs-insert
---
The key difference between Selection Sort and Insertion Sort is that most of the work done in Selection Sort is in tge "Select" (finding) step and most of the work done in Insertion Sort is in the "Insert" step. 
```

2. Depending on the implementation and the data, insertion sort can, in the best case, be faster than selection sort. 

