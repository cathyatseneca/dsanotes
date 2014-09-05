# The runtime stack

The run time stack is basically the way your programs store and handle your local non-static variables.  Think of the run time stack as a stack of plates.  With each function call, a new "plate" is placed onto the stacks.  local variables and parameters are placed onto this plate.  Variables from the calling function are no longer accessible (because they are on the plate below). When a function terminates, the local variables and parameters are removed from the stack.  Control is then given back to the calling function.  Understanding the workings of the run time stack is key to understanding how and why recursion works

