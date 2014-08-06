## Big-O, Little-O, Theta, Omega

Big-O, Little-o, Omega, and Theta are formal notational methods for stating the growth of resource needs (efficiency and storage) of an algorithm.  There are four basic notations used when describing resource needs.  These are:  O(f(n)), o(f(n)), Ω(f(n)), and Θ(f(n)).  (Pronounced, Big-O, Little-O, Omega and Theta  respectively)

### Formally:

"T(n) is O(f(n))" if for some constants \\(c\\) and \\(n_0\\), \\(T(n)<=cf(n)\\) for all \\(n >= n_0\\)

"T(n) is Ω(f(n))" if for some constants \\(c\\) and \\(n_0\\), \\(T(n)>=cf(n)\\) for all \\(n >= n_0\\)

"T(n) is Θ(f(n))" if T(n) is O(f(n)) AND T(n) is Ω(f(n))

"T(n) is o(f(n))" if T(n) is O(f(n)) AND T(n) is NOT Θ(f(n))

### Informally:

"T(n) is O(f(n))" basically means that f(n) describes the upper bound for T(n)

"T(n) is Ω(f(n))" basically means that f(n) describes the lower bound for T(n)

"T(n) is Θ(f(n))" basically means that f(n) is both the upper and lower bound for T(n)

"T(n) is o(f(n))" basically means that f(n) is the upper bound for T(n) but that T(n) can never be equal to f(n)


#### Another way of saying this:

"T(n) is O(f(n))" growth rate of T(n) <= growth rate of f(n)

"T(n) is Ω(f(n))" growth rate of T(n) >= growth rate of f(n)

"T(n) is Θ(f(n))" growth rate of T(n) == growth rate of f(n)

"T(n) is o(f(n))" growth rate of T(n) < growth rate of f(n)


### An easy way to think about big-O

The math in big-O analysis can often be intimidates students.  One of the simplest ways to think about big-O analysis is that it is basically a way to apply a rating system for your algorithms (like movie ratings).  It tells you the kind of resource needs you can expect the algorithm to exhibit as your data gets bigger and bigger.  From best  (least resource requirements ) to worst, the rankings are:  O(1), O(\\(log n)\\), O(\\(n)\\), O(\\(n log n)\\), O(\\(n^2)\\), O(\\(n^3)\\),  O(\\(2^n)\\).  Think about the graphs in the grow rate section.  The way each curve looks.  That is the most important thing to understand about algorithms analysis

### What all this means

Let's take a closer look a the formal definition for big-O analysis

"T(n) is O(f(n))" if for some constants \\(c\\) and \\(n_0\\), \\(T(n)<=cf(n)\\) for all \\(n >= n_0\\)

The way to read the above statement is as follows.  n is the size of the data set.  f(n) is a function that is calculated using n as the parameter.  O(f(n)) means that the curve described by f(n) is an upper bound for the resource needs of a function.  that means that if we were to draw a graph of the resource needs of a particular algorithm, it would fall under the curve described by f(n).  What's more, it doesn't need to be under the exact curve of f(n).  It could be under a constant *scaled* curve for f(n)... so instead of having be under the \\(n^2\\) curve, it can be under the \\(10n^2\\) curve or the \\(20n^2\\)curve.  In fact it can be any constant, as long as it is a constant.

Furthermore, the statement does not need to be true for all data sizes.  The \\(n >= n_0\\) portion means that as long as you can find a data size for which the statement is true, and it never becomes untrue for all data sizes larger than that value, then you have met the criteria for big-O


