# Illustrated Example

When writing the code for a linked list, you must be very careful about the order in which you do each step of a function.  It is important that you don't lose bits of the list as you try to add and remove nodes.  The following shows pictorially how insertion and removal could be done.  When you write your own linked list, pictures will help.

Note:  In each of the following illustration a code segment will be used to show the code needed to obtain the desired result.  IT IS NOT NECESSARILY THE FULL CODE TO A FUNCTION.

## Initialization

Typically a linked list starts off empty.  start_ and curr_ are both NULL.  The fact that start_ is NULL means that the list is empty.

### Initialization Code Segment

```c
start_=NULL;
curr_=NULL;
```


### Make the function call:  insertAfter(3.5);

Since the list is empty, all we need to do is create a new node and make start_ and curr_ point to it.  In the new node, the next_ pointer should be NULL as there is no next node:

```c
Node* temp=new Node;
temp->data_=newdata;
temp->next_=NULL;
start_=temp;
curr_=temp;
```
