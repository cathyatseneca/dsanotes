# Quick Sort

This sort is fast and does not have the extra memory requirements of MergeSort.  On average its run time is O(n log n) but it does have a worst case run time of O(n2)

QuickSort works like this:

1.	Pick a value from the array as the pivot
2.	Let i=front, j= back
3.	advance i until you find a value arr[i] > pivot
4.	move j towards front of array until arr[j] < pivot
5.	swap these arr[i] and arr[j].
6.	repeat step 3 to 5 until i and j meet
7.	The meeting point is used to break the array up into two pieces
8.	QuickSort these two new arrays

A simple version of the algorithm can be written as:

```c
template <class TYPE>
void QuickSort(vector<TYPE>& arr, int left, int right){
  if(right-left <=3){
    InsertionSort(arr,left,right);
  }
  else{
    int pivotpt=right;
    int i=left;
    int j=right-1;
    TYPE pivot=arr[pivotpt];
    while(i<j){
      while(arr[i]<pivot) i++;
      while(arr[j]>pivot) j--;
      if(i<j)
        swap(arr[i++],arr[j--]);
    }
    swap(arr[i],arr[pivotpt]);
    QuickSort(arr,left,i-1);
    QuickSort(arr,i+1,right);
  }
}

template <class TYPE>
void QuickSort(vector<TYPE>& arr){
  QuickSort(arr,0,arr.size()-1);
}
```
The idea of a quicksort is that with each call, the quicksort algorithm would break the vector up into two parts.  The best thing that can happen is that each time we get pieces that are of equal size (ie we get two pieces that is half the size of the original vector).  As you will recall from binary search, you can only half something log n times (where n is the size of the vector) before you get a vector of size 0.  Thus, for the best possible case, the runtime is O(n log n).

The worst thing that can happen for the quicksort algorithm is to choose a pivot such that we end up getting a pivot point that breaks up the vector into an empty vector and a vector containing everything else every single time.  If you do this, you will end up with not reducing the size of the vector by much (just one for the pivot) and thus, your work will be almost as much as it was to begin with.  The worst case run time is O(\\n^2\\)

## Median of Three Partitioning

The average runtime for quicksort is also O(n log n).

The algorithm that is shown above chooses the last element in the vector as the pivot.  This was done for simplicity but is actually not very good.  If the elements are random, then using the end of the array is not bad.  However, if the data is nearly sorted to begin with then picking the end point could very well mean picking the biggest value.  This would create the worst case scenario where one vector was empty and the other contained everything else.

Recall that the best possible scenario occurs when we break down the list into two pieces of the same size.  To do this, our pivot must be the median value.  The median is the number where half of the other numbers are below it and half the other numbers are above it.  Thus, if our pivot was the median of the list each and every time, we would end up with the best case scenario.  However, finding the median is not an easy problem to solve quickly so instead of trying to find the exact median, one strategy is to choose the median of three values in the vector (use the three values like a sampling of the population.  Like polling!)  This can be done by looking at the first, last and middle element.  From here choose the median value of the three as the pivot.
