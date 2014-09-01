# Analysis of Binary Search

The following is the code for a binary search.  Similar to linear search, we make an assumption that the size() function has a constant run time.  For a binary search to work the data must be sorted.  In this case we assume that the data is sorted from smallest (at arr[0]) to biggest (at arr[size-1]).

The second part that is important to remember about a binary search is that you need to be able to access the any item given its index in constant time.  If that is not possible, the analysis will fail.

```c
template <class TYPE>
int BinarySearch(const vector<TYPE>& arr, const TYPE& key){
  int rc=-1;
  int low=0;
  int high=arr.size()-1;
  int mid;
  while(low<=high && rc==-1){
    mid=(low+high)/2;
    if(arr[mid] > key)
      high=mid-1;
    else if(arr[mid] < key)
      high= mid+1;
    else
      rc=i;
  }/*while*/
  return rc;
}
```
Like a Linear search, the determining factor on runtime for binary search is also the loop:

```c
  while(low<=high && rc==-1){
    mid=(low+high)/2;
    if(arr[mid] > key)
      high=mid-1;
    else if(arr[mid] < key)
      low= mid+1;
    else
      rc=i;
  }/*while*/

```

The code within this loop is constant and thus, the question really becomes how many times will this loop run?

Again, we can either find the key or not find the key.

If the vector does NOT contain the key, how long will it take to run?

At the beginning high - low = n -1.  With each iteration we "move" high or low towards each other so that their difference is halved (their new values are near the mid point)

By doing this, it would take the loop at most   iterations before low>high

Thus for an unsuccessful search, the function's runtime O(log n)

For a successful search we might still need to search when high==low and to get to that point would also require  iterations.  Thus, the worst case runtime for this function when the key is found is also O(log n)

Therefore, the worst case runtime for this function is O(log n)

