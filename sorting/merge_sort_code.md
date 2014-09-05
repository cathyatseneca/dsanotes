# Merge Sort Implementation

Now, the merge algorithm is an O(n) algorithm as we pick n items between two lists.  However, it depends on having two lists that are already sorted...So we must first get a list into that state.

We also need a second array for storaging the merged list.  Our mergesort function should also not look any different than any other sorting function (ie all you need for a sorting function is the array).  The sorting algorithm creates a temporary array once and passes that into a recursive function to do all the work.  The idea here is that we don't want to allocate memory on each merge... instead we can just use one array that stays around for the entire process.

```c
template <class TYPE>
void mergeSort(vector<TYPE>& arr){
  vector<TYPE> tmp(arr.size());
  //call mergeSort with the array, the temporary
  //and the starting and ending indices of the array
  mergeSort(arr,tmp,0,arr.size()-1);
}
```
This algorithm is recursive in nature.  The idea is that we have a function that if it works, will sort an array between start and end inclusive.   So how it works is we start with the big array and we mergeSort() each of the two halves of it.  We can then merge the two lists together. to form a sorted list.

The base case for this algorithm is when we have an array that is one element long (ie start and end are the same).  A list that has one element is always sorted.  So if we merged two of these lists that are one element big together, we will create a list that is 2 elements and sorted.

```c
//this function sorts arr from index start to end
template <class TYPE>
void mergeSort(vector<TYPE>& arr, vector<TYPE>& tmp, int start, int end){
  if (start<end){
    int mid=(start+end)/2;
    mergeSort(arr,tmp,start,mid);
    mergeSort(arr,tmp,mid+1,end);
    merge(arr,tmp,start,mid+1,end);
  }
}
```
This merge function is the code as stated in the previous  description

```c
/*This function merges the two halves of the array arr into tmp and then copies it back into arr*/
template <class TYPE>
void merge(vector<TYPE>& arr, vector<TYPE>& tmp, int start,
                                         int start2, int end){
  int aptr=start;
  int bptr=start2;
  int i=start;
  while(aptr<start2 && bptr <= end){
    if(arr[aptr]<arr[bptr])
      tmp[i++]=arr[aptr++];
    else
      tmp[i++]=arr[bptr++];
  }
  while(aptr<start2){
    tmp[i++]=arr[aptr++];
  }
  while(bptr<=end){
    tmp[i++]=arr[bptr++];
  }
  for(i=start;i<=end;i++){
    arr[i]=tmp[i];
  }
}
```
[Merge sort animation: http://cathyatseneca.github.io/DSAnim/web/merge.html](http://cathyatseneca.github.io/DSAnim/web/merge.html)


