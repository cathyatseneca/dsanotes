## insertion at start of list

### step 1: call goStart()

```c
goStart();
```

![goStart(): step 1](../assets/gostart.png)

### step 2: make a new node

```c
curr_->next_=temp;
```

![insertFront: step 2](../assets/linkedlist6a.png)

### step 3: make start point to new node


```c
curr_->next_=temp;
```
![insertFront: step 3](../assets/linkedlist6b.png)

### step 3: point curr_ to new node

```c
curr_=temp;
```
![insertFront: step 4](../assets/linkedlist6c.png)

