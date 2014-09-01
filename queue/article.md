# Queue Implementations

This section will look at how to efficiently implement a queue using both an array and a linked list.  Like a stack, a queue is also a special type of list. While a queue is a "line up" the ideas of front and back are not meant to be taken literally.  The key is to understand that a Queue is a FIFO (first in first out) structure.  That is the item to be removed is the oldest item in the list.  as long as this is true, it doesn't matter where exactly the items get put into the queue or where it is removed.


## Linked List implementation


To implement a queue using a linked list, we have to consider the type of linked list we would use and which end of the list we would want to insert to.

The simplest linked list is a singly list.  If this linked list was implemented with just a pointer to the first node, insertion would be O(1) at front of list, O(n) at back of list.  removal is O(1) at front of list and O(n) at back of list. If we added an end pointer to the list, then insertion to back of list can be O(1) also, however removing from the back of the list will still be O(n).

Now, if we perform enqueue by inserting at the front of the list, the oldest item would be at the back of the list and thus, dequeue would have to be done there.  enqueue would be quick O(1) but dequeue would be slow O(n).  However, if we enqueue by inserting to the end of the list using a linked list that tracks the last node, then the oldest item would be at the front of the linked list.  This will allow us to perform enqueue and dequeue in O(1) time.

## Array Implementation

Implementing a queue with an array is a bit more complicated than using a stack.

Consider the typical way we implement a list using an array.  To insert a value to the front of the list, we would move all existing values to an element that is one index higher in the array then add the new value to the first element.  To remove a value we would move all in the array to element one index lower, overwriting the first element.  Both the removal and insertion are O(n) operations.

Thus, if we were to use this list, and performed enqueues at the front of the list, the enqueue function would be O(n).  Enqueuing in this manner would mean that the oldest item would be at the back of the array.  Removing from back of list is fast so we can accomplish this in O(1) time as long as we track where the last item is.

Now... if we were to enqueue to the end of the list, the oldest item would be at the front, and thus removal would have to be done to the front of the list.  In this case, enqueue would be fast O(1) but dequeue would be slow O(n).

So clearly we need to come up with a better way to handle this.

One way that we can handle this is to track two indices instead of one.  The first is the index of the element at the front of the list.  The second is the index of the element at the back of the list.  When you insert, insert to the index of the back element and increment the index for back.  When you remove, remove by incrementing the index of the front.  The second part of the implementation is that we need to treat the array as if it is a ring.  That is the the index element, is the first element.  If we do not, we will quickly create a list with lots of unused space at the front of the list.
