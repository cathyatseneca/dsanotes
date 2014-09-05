# Stack Implemenations

There are two general ways to implement a stack.  As a stack is essentially a list with a restriction on the operations of a list, we can use either an array or a linked list to implement a stack.  The key to understanding how to do this efficiently is to understand the nature of a stack.

A stack is a FILO (first in last out) structure.  Thus, the most important thing to remember about it is that when you remove an item from the stack, you want to remove the newest item, where ever that may be. How it is stored internally (which end of the list do you insert into for example) does not matter as long as you always remove the newest item.  Thus, the question of how to implement a stack comes down to choosing an algorithm such that the operations can be completed as quickly as possible.

Recall that the operations are as follows:

* **push** - add a new item to the stack
* **pop** - removes top item from the stack
* **initialize** - create an empty stack
* **isEmpty** - tests for whether or not stack is empty
* **isFull** - tests to see if stack is full and cannot grow (not always needed)
* **top** - looks at value of the top item but do not remove it

### Array Implementation

With a list that implemented as an array we typically start by creating an array that is bigger than what we need.  To add a value to the end of an array is a constant time operation as long as we track where the end is.  If we were to do that, the most recently added item will be at the back of the array.  Removing that item simply involves decreasing the end of array tracker by one.

Check out this animation for details:

[Stack Implemented with an array http://cathyatseneca.github.io/DSAnim/web/arraystack.html](http://cathyatseneca.github.io/DSAnim/web/arraystack.html)

### Linked List Implementation

To implement a stack using a linked list, we have to consider the type of linked list we would use and which end of the list we would want to insert to.

The simplest linked list is a singly list.  If this linked list was implemented with just a pointer to the first node, insertion would be O(1) at front of list, O(n) at back of list.  removal is O(1) at front of list and O(n) at back of list. If we added an end pointer to the list, then insertion to back of list can be O(1) also, however removing from the back of the list will still be O(n).

If we were to insert always at front of list, then the most recently added item would be at the front of the list.  Thus, removal must occur from the front as we always remove the most recently added item.  Since we can do both quickly with a simple singularly linked list, that is all we will need to do.
