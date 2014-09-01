

## goNext()

```c
curr_=curr_->next_;
```

![point to next node](../assets/gonext.png)

## goPrev()

### step 1, after ensuring that curr is not pointing to first node, make a temp pointer to first node

```c
if(curr_!=start_){
  Node* temp=start_; //step 1
}
```
![step1](../assets/goprev1.png)

### step 2: move temp down the list

```c
while(temp->next_!=curr_){
    temp=temp->next_;
}
```
![step2](../assets/goprev2.png)

### step 3: point curr_ to same node as temp

```c
curr_=temp;
```
![step3](../assets/goprev3.png)

## goStart()
```c
curr_=start_;
```
![goStart(): step 1](../assets/gostart.png)
