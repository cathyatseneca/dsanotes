## remove second node


### step 1: call goNext()

```c
goNext();
```

![goStart(): step 1](../assets/linkedlist7a.png)

### step 2: make 3 pointers that point to node before, node after, and current node

```c
Node* pr=prev();
Node* nx=next();
Node* rem=curr();

```

![insertFront: step 2](../assets/linkedlist7b.png)

### step 3: point the next_ pointer of the previous node and curr_ to the node after the one we want to remove


```c
pr->next_=curr_=nx;
```
![insertFront: step 3](../assets/linkedlist7c.png)

### step 4: deallocate the node

```c
delete rem;
```
![insertFront: step 4](../assets/linkedlist7d.png)

