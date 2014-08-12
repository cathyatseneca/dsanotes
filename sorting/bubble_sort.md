# Bubble Sort


A bubble sort is one of the simplest sorts to write.  The idea behind a bubble sort is to start at the beginning of the array and swap adjacent elements that are not in order.  Repeat this n-1 times where n is the size of the array and the array will be sorted.

```c
void bubble(int array[],int sz){
	int i,j;
	int tmp;
	for(i=0;i<sz-1;i++){
		for(j=0;j<sz-i-1;j++){
			if(array[j] > array[j+1]){
				//swap arr[j] and arr[j+1]
				tmp=array[j];
				array[j]=array[j+1];
				array[j+1]=tmp;
			}
		}
	}
}
```

[Bubble sort animation: http://cathyatseneca.github.io/DSAnim/web/bubble.html](http://cathyatseneca.github.io/DSAnim/web/bubble.html)
