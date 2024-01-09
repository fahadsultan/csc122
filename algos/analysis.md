# Analysis

Algorithms are the most important and durable part of computer science.

This is because they can be studied in a way **independent of any programming-language** and **machine hardware**. 

This means that we need techniques that enable us to compare the efficiency of algorithms without implementing them. 

Our two most important tools are:

1. RAM model of computation 
2. Asymptotic Analysis of worst-case complexity.

Assessing algorithmic performance makes use of the “big Oh” notation that, proves essential to compare algorithms and design more efficient ones. 

While the hopelessly _"practical"_ person may blanch at the notion of theoretical analysis, we present the material because it really is useful in thinking about algorithms.

This method of keeping score will be the most mathematically demanding part of this book. But once you understand the intuition behind these ideas, the formalism becomes a lot easier to deal with.

## The RAM Model of Computation

Machine-independent algorithm design depends upon a hypothetical computer called the Random Access Machine or RAM. Under this model of computation, we are confronted with a computer where:

- Each _simple_ operation (+, -, *, /, if, call, return, etc.) takes exactly one time step.

- Loops and subroutines are _not_ considered simple operations. Instead, they are the composition of many single-step operations. It makes no sense for sort to be a single-step operation, since sorting 1,000,000 items will certainly take much longer than sorting 10 items. The time it takes to run through a loop or execute a subprogram depends upon the number of loop iterations or the specific nature of the subprogram.

- Each memory access takes exactly one time step. Further, we have as much memory as we need. The RAM model takes no notice of whether an item is in cache or on the disk. It also ignores the fact that memory access time is not uniform. In the RAM model, we can access any memory location in the same amount of time.

Under the RAM model, we measure run time by counting up the number of steps an algorithm takes on a given problem instance. If we assume that our RAM executes a given number of steps per second, this operation count converts naturally to the actual running time.
The RAM is a simple model of how computers perform. Perhaps it sounds too simple. After all, multiplying two numbers takes more time than adding two num- bers on most processors, which violates the first assumption of the model. Fancy compiler loop unrolling and hyperthreading may well violate the second assump- tion. And certainly memory access times differ greatly depending on whether data sits in cache or on the disk. This makes us zero for three on the truth of our basic assumptions.

And yet, despite these complaints, the RAM proves an excellent model for understanding how an algorithm will perform on a real computer. It strikes a fine balance by capturing the essential behavior of computers while being simple to work with. We use the RAM model because it is useful in practice.

Every model has a size range over which it is useful. Take, for example, the model that the Earth is flat. You might argue that this is a bad model, since it has been fairly well established that the Earth is in fact round. But, when laying the foundation of a house, the flat Earth model is sufficiently accurate that it can be reliably used. It is so much easier to manipulate a flat-Earth model that it is inconceivable that you would try to think spherically when you don’t have to.1

The same situation is true with the RAM model of computation. We make an abstraction that is generally very useful. It is quite difficult to design an algorithm such that the RAM model gives you substantially misleading results. The robustness of the RAM enables us to analyze algorithms in a machine-independent way.

### Best, Worst, and Average-Case Complexity

Using the RAM model of computation, we can count how many steps our algorithm takes on any given input instance by executing it. However, to understand how good or bad an algorithm is in general, we must know how it works over all instances.
To understand the notions of the best, worst, and average-case complexity, think about running an algorithm over all possible instances of data that can be fed to it. For the problem of sorting, the set of possible input instances consists of all possible arrangements of n keys, over all possible values of n. We can represent each input instance as a point on a graph (shown in Figure 2.1) where the x-axis represents the size of the input problem (for sorting, the number of items to sort), and the y-axis denotes the number of steps taken by the algorithm in this instance.
These points naturally align themselves into columns, because only integers represent possible input size (e.g., it makes no sense to sort 10.57 items). We can define three interesting functions over the plot of these points:

* The _worst-case complexity_ of the algorithm is the function defined by the maximum number of steps taken in any instance of size _n_. This represents the curve passing through the highest point in each column.

* The _best-case complexity_ of the algorithm is the function defined by the minimum number of steps taken in any instance of size _n_. This represents the curve passing through the lowest point of each column.

* The _average-case complexity_ of the algorithm, which is the function defined by the average number of steps over all instances of size _n_.

The worst-case complexity proves to be most useful of these three measures in practice. Many people find this counterintuitive. To illustrate why, try to project what will happen if you bring n dollars into a casino to gamble. The best case, that you walk out owning the place, is possible but so unlikely that you should not even think about it. The worst case, that you lose all n dollars, is easy to calculate and distressingly likely to happen. The average case, that the typical bettor loses 87.32% of the money that he brings to the casino, is difficult to establish and its meaning subject to debate. What exactly does average mean? Stupid people lose more than smart people, so are you smarter or stupider than the average person, and by how much? Card counters at blackjack do better on average than customers who accept three or more free drinks. We avoid all these complexities and obtain a very useful result by just considering the worst case.

The important thing to realize is that each of these time complexities define a numerical function, representing time versus problem size. These functions are as well defined as any other numerical function, be it y = x2 − 2x + 1 or the price of Google stock as a function of time. But time complexities are such complicated functions that we must simplify them to work with them. For this, we need the “Big Oh” notation.

## Big Oh Notation

The best, worst, and average-case time complexities for any given algorithm are numerical functions over the size of possible problem instances. However, it is very difficult to work precisely with these functions, because they tend to:

* _Have too many bumps_ – An algorithm such as binary search typically runs a bit faster for arrays of size exactly n = 2k − 1 (where k is an integer), because the array partitions work out nicely. This detail is not particularly significant, but it warns us that the exact time complexity function for any algorithm is liable to be very complicated, with little up and down bumps as shown in Figure 2.2.

* _Require too much detail to specify precisely_ – Counting the exact number of RAM instructions executed in the worst case requires the algorithm be specified to the detail of a complete computer program. Further, the precise answer depends upon uninteresting coding details (e.g., did he use a case statement or nested ifs?). Performing a precise worst-case analysis like

$$T(n)=12754n^2 +4353n+834lg_2n+13546$$

would clearly be very difficult work, but provides us little extra information than the observation that “the time grows quadratically with n.”

It proves to be much easier to talk in terms of simple upper and lower bounds of time-complexity functions using the Big Oh notation. The Big Oh simplifies our analysis by ignoring levels of detail that do not impact our comparison of algorithms.

The Big Oh notation ignores the difference between multiplicative constants. The functions f(n) = 2n and g(n) = n are identical in Big Oh analysis. This makes sense given our application. Suppose a given algorithm in (say) C language ran twice as fast as one with the same algorithm written in Java. This multiplicative factor of two tells us nothing about the algorithm itself, since both programs imple- ment exactly the same algorithm. We ignore such constant factors when comparing two algorithms.

The formal definitions associated with the Big Oh notation are as follows:

* $f (n) = O(g(n))$ means $c · g(n)$ is an _upper bound_ on f (n). Thus there exists some constant c such that f (n) is always ≤ c · g(n), for large enough n (i.e. , n ≥ n0 for some constant n0).

* $f(n) = Ω(g(n))$ means $c · g(n)$ is a _lower bound_ on f(n). Thus there exists some constant c such that f(n) is always ≥ c · g(n), for all n ≥ n0.

* $f(n) = Θ(g(n))$ means $c1 · g(n)$ is an _upper bound_ on f(n) and c2 · g(n) is a lower bound on f(n), for all n ≥ n0. Thus there exist constants c1 and c2 such that f (n) ≤ c1 · g(n) and f (n) ≥ c2 · g(n). This means that g(n) provides a nice, tight bound on f(n).

Got it? These definitions are illustrated in Figure 2.3. Each of these definitions assumes a constant n0 beyond which they are always satisfied. We are not concerned about small values of n (i.e. , anything to the left of n0). After all, we don’t really care whether one sorting algorithm sorts six items faster than another, but seek which algorithm proves faster when sorting 10,000 or 1,000,000 items. The Big Oh notation enables us to ignore details and focus on the big picture.

Make sure you understand this notation by working through the following ex- amples. We choose certain constants (c and n0) in the explanations below because they work and make a point, but other pairs of constants will do exactly the same job. You are free to choose any constants that maintain the same inequality—ideally constants that make it obvious that the inequality holds: