# Selection Sort

The selection sort algorithm works by selecting the smallest value in the unsorted portion of the array then swapping it with the first value of the unsorted portion of the array.

```c
void selectionSort(int arr[],int size){
	int minIdx;
	int tmp;
	for(int i=0;i<size;i++){
		minIdx=i;
		for(int j=i;j<size;j++){
			if(arr[j] < arr[minIdx]){
				minIdx=j;
			}
		}
		//swap
		tmp=arr[i];
		arr[i]=arr[minIdx];
		arr[minIdx]=tmp;
	}
}
```
[Selection sort animation: http://cathyatseneca.github.io/DSAnim/web/selection.html](http://cathyatseneca.github.io/DSAnim/web/selection.html)
