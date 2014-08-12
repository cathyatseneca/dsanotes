# List Declaration

A linked list could be defined as the following.  (Note that there are other ways to encapsulate the idea of linked list.  This is just one way.):

class Llist{
  Node* start_;
  Node* curr_;
public:
....
};

The public member functions for a linked list should then provide methods for accessing and manipulating the data stored in the linked list.

In the following discusion we will assume we are writing a linked list of doubles

## Functions for Node Access

```c
Node* start(); //returns a pointer to the first node
Node* curr();  //returns a pointer to the the current node
Node* next();  //returns a pointer to the node after the
               //current node.  If curr is NULL return NULL
Node* prev();  //returns a pointer to the node before the
               //current node.  If curr is NULL return NULL
int data(double& dat); //if the curr is not NULL, pass the
                       //data at the node back through dat

```

## Functions for Manipulating the Linked List
```c
/*make curr_ point at the previous node if possible.  If successful return true, otherwise return false*/
int goPrev();

/*make curr_ point at the next node if possible. If successful return true, otherwise return false*/
int goNext();

/*makes the first node the current node*/
void goStart();

/*makes the last node the current node*/
void goeEnd();

/*insert a node after the current node containing newdata as the data for the node.  curr_ should point at the newly added node.  return the address of the node inserted if successful, null pointer otherise*/
Node* insertAfter(double newdata);

/*insert a node before the current node containing newdata as the data for the node.  curr_ should point at the newly added nodereturn the address of the node inserted if successful, null pointer otherise*/
Node* insertBefore(double newdata);

/*insert a node at start of list*/
Node* insertFront(double data);

/*insert a node at the end of the list*/
Node* insertEnd(double data);

/*removes the node pointed to by curr_.  If the node removed was the last node in the list make curr_ point at the new last node.  Otherwise, curr_ should point at the node after one the one that was just removed.*/
void remove();

/*remove node from front of the list*/
Node* removeFront()

/*remove node from end of the list*/
void removeEnd();

```

## Initialization and Cleanup

The list also needs to be properly initialized.  When the list goes out of scope, resources must be freed up.  Therefore a constructor and destructor are also needed

