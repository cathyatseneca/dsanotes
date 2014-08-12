# Array Implementation

Queues are slightly more difficult to implement using arrays than a stack.  The reason is that with a stack, we can very efficiently add/remove to the end of the array.  However, with a queue, no matter which end you choose to add data to, the other end must be used for removing data.  If we use the standard list implemenation method for  insertion and removal to front and back, we will end up having to shuffle data for at least one of the two operations.  This could make the queue very inefficient.

Another way to implement a queue using arrays is to store a front and end index.  To add an element put the item in array[end] and increment end.  To remove an item, remove it from array[front] and increment front.  Treat the array as circular so that the element after the last element is array[0].


