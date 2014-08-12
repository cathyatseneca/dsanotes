## How to do an Analysis

To look at how to perform analysis, we will start with a performance analysis of the following C++ function for a linear search:

```c
template <class TYPE>
int linearSearch(const vector<TYPE>& arr, const TYPE& key){
  	int rc=-1;
  	for(int i=0;i<arr.size()&& rc==-1;i++){
   	 	if(arr[i]==key){
   	 		rc=i;
    	}
  	}
  	return rc;
}
```

We will make a few assumptions.  arr.size() runs in constant time.  That is no matter how big the array is, arr.size() takes the same amount of time to run.

When we run the above algorithm, 2 things can occur.  The first is that we will find the key.  The second is that we won't.  The worst case scenario occurs when key is not in the array.  Thus, let us start by performing the analysis base on that worst case.

### Analysis of an Unsuccessful Search

Let n represent the size of the array arr.
Let T(n) represent the number of operations necessary to perform linear search on an array of n items.

Looking at the code, we see that there are some operations that we have to perform one time no matter what:

	int rc = -1
	int i = 0
	return rc;

So here, we can count these as 3 operations that have to occur at least once regardless of the size of the array.

Now we then look at the rest of the code, if our search was to fail we would have to do all the other statements in the for loop (with the exception of rc=i) once per piece of data in the array.

The following has to be done each time through the loop:

	i<arr.size() && rc == -1   --> 3 operations
	i++                        --> 1 operation
	if(arr[i]==key)            --> 2 operations

6 operations in the loop total

Now... some of you may also think... should the function call arr.size() be an operation itself?  or what about the [i] in arr[i]?  The truth is, it doesn't actually matter if we count them or not.  Let's take a look at why this is the case by finishing this analysis.

Now... using the above we can express T(n) as follows:

T(n) = 6n + 3

The 6n comes from the 6 operations that we do each time through the loop.  We have n elements in the array.  Thus, the loop must run 6n times.

The + 3 comes from the 3 operations that we always have to do no matter what.

Thus the expression for the number of operations that is performed is:

T(n) = 6n + 3


Now, imagine n becoming a very very large number.  As n gets bigger and bigger, the 3 matters less and less.  Thus, in the end we only care about 6n.  6n is the *dominating term* of the polynomial.  This is similar to this idea.  If you had 6 dollars, then adding 3 dollars is a significant increase to the amount of money you have.  However, if you had 6 million dollars, then 3 dollars matter very little.

Using the dominating term, we can say that the linear search algorithm has a run time that never exceeds the curve for n.  In other words, linear search is O(n).


Now... can we actually prove this?

According to the formal definition for big-O

"T(n) is O(f(n))" if for some constants \\(c\\) and \\(n_0\\), \\(T(n)<=cf(n)\\) for all \\(n >= n_0\\)


In other words... to prove that T(n) = 6n + 3 is O(n) we must find 2 constants \\(c\\) and \\(n_0\\) such that the statement \\(t(n) <= cn\\) is true for all \\(n >= n_0\\)


The important part about this... is to realize that we can pick any constant we want.  So, I will pick the c = 10.  (in fact, I can pick any number > 6).   and \\(n_0 = 1\\)

\\(T(n) = 6n + 3 \\)  <br />
\\(T(0) = 6(0) + 3 = 3 \\) <br />
\\(T(1) = 6(1) + 3 = 9 \\) <br />
\\(T(2) = 6(2) + 3 = 15 \\) <br />
\\(T(3) = 6(3) + 3 = 21 \\) <br />
...

our function f(n) = n.

Thus:

\\(c f(n) = n\\)  <br />
\\(c f(0) = 10(0) = 0\\) <br />
\\(c f(1) = 10(1) = 10\\) <br />
\\(c f(2) = 10(2) = 20\\) <br />


As you can see the statement T(n) <= cn is true for any value of all \\(n >= n_0\\)

Thus, we have proven that the function is O(n) because we were able to find the two constants \\(c) and \\(n_0\\) needed for the T(n) to be O(n)

This is also the reason why it did not matter if we counted the operations for the size() function call or the [i] operator.  If we counted both of them,

T(n) = 8n + 3

The dominating term would still be 8n.

The proof would go exactly the same way except that we can't use \\(n_0 = 1 \\) as the statement T(n) < cn is not true when n == 1.  However, when n = 2, T(n) = 19 and cn would be 20. Thus, it would be true and stays true for all values of n > 2.


### Average case analysis

In the previous analysis, we assumed we wouldn't find the data and thus the worst possible case of searching through the entire array was used to do the analysis.  However, what if the item was in the array?

Assuming that key is equally likely to be in any element, we would have to search through n elements at worst and n/2 elements on average.

Now since we will at some point find the item, the statement inside the if will also be performed.  Thus, we will have 4 operations that we must run through once.

	int rc = -1
	int i = 0
	rc=i
	return rc;

These other operations will also run for each iteration of the loop:


	i<arr.size() && rc == -1   --> 3 operations
	i++                        --> 1 operation
	if(arr[i]==key)            --> 2 operations


The difference is we do not expect that the loop would have to run through the entire array.  On average we can say that it will go through half of the array.

Thus:

T(n) = 6 * 0.5 n + 3 = 3n + 3

Now... as we said before... the constant of the dominating term does not actually matter.  3n is still n.  Our proof would go exactly as before for a search where the key would not found.







