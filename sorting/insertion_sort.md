# Insertion Sort

The insertion sort algorithm works by looking at the array as if it is being filled in.  The idea is that the array starts off in the first iteration as if it has only one element in it.  The numbers that come after are then inserted into the "array" at the correct position.  This is continued until all values in the entire array have been properly "inserted"


```c
void insertionSort(int arr[],int size){
	int curr;
	int i,j;
	for(i=0;i<size;i++){
		curr=arr[i];
		for(j=i;j>0 && arr[j-1] > curr;j--){
			arr[j]=arr[j-1];
		}
		arr[j]=curr;
	}
}
```

[Insertion sort animation: http://cathyatseneca.github.io/DSAnim/web/insertion.html](http://cathyatseneca.github.io/DSAnim/web/insertion.html)
