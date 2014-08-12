# Nodes

If we want to store some doubles our node declaration would be:
```c
struct Node{
  double data_;    // the data portion of the node
  Node* next_;     // a pointer to the next node
};
```

To create linked lists that hold other data types the data portion of a node would need to be a different data type.  You could have a linked lists that hold user defined data datatypes.

```c
class Hamster
  char name_[50];
  int age_;
public:
....
};

//Each node holds one instance of Hamster.
struct Node{
  Hamster data_;
  Node* next_;
};
```

Your linked lists can also be template classes.
```c
template <class TYPE>
struct Node{
  TYPE data_;
  Node<TYPE>* next_;
};
```

If you create a template node, you will also need to create a template list.

Even though we have used a struct to define a Node, it is also possible to use a class.  If you use a class to define a Node, you will need to write functions to access the data members.  Another method of handling a Node class is by using friends.  You could make the list a friend of your Node class so that access to data is restricted to the list.

Every list MUST have a pointer to a node in the list (usually the beginning).  This pointer should point to a node that will allow access to all the other nodes.  It may also be useful to have an internal pointer that could be used to manipulate the list.




