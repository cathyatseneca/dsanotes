# Merge Sort


The merge sort works on the idea of merging two already sorted lists.  If there existed two already sorted list, merging the two together into a single sorted list can be accomplished in O(n) time.

## Merge algorithm:

The algorithm to do so works as follows:

* Have a way to "point" at the first element of each of the two list
* compare the values being pointed at and pick the smaller of the two
* copy the smaller to the merged list, and advance the "pointer" of just that list to the next item.
* Continue until one of the list is completely copied then copy over remainder of the rest of the list

### Example

Here we have 2 sorted lists.  Note that being already sorted is a must.  This algorithm does not work on unsorted lists.
![merge1](../assets/merge1.png)


look at first element of each list and find smaller, copy it to the resulting list, then advance pointer.
![merge2](../assets/merge2.png)


between 2 and 3, 2 is smaller:
![merge3](../assets/merge3.png)


between 3 and 7, 3 is smaller:
![merge4](../assets/merge4.png)


between 5 and 7, 5 is smaller:
![merge5](../assets/merge5.png)


between 6 and 7, 6 is smaller:
![merge6](../assets/merge6.png)


between 7 and 9, 7 is smaller:
![merge7](../assets/merge7.png)


between 8 and 9, 8 is smaller:
![merge8](../assets/merge8.png)


list 2 is now empty, copy rest of list 1 over
![merge9](../assets/merge9.png)

