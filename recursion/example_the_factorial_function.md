# Example: the Factorial Function

Write the function:
```c
int factorial(int n);
```
This function returns n! (read n factorial) where n is an integer.
```
n!=n* n-1* n-2*....2*1  by definition 0! is 1
```
for example
```
if n==5, then n! would be 5! = 5*4*3*2*1=120
```

To write this we must come up with several things.   What is the base case?  In other words, for what value of n do I immediately know what the answer would be without doing more than a simple operation or two.

In this case, we know what 0! is.  It is 1 by definition
1! is another base case because 1! is simply 1 as well.

So the base case occurs when n is 0 or 1.  In this case, the function can simply return 1

Now the recursive case.  How can we state the solution in terms of itself.  First thing you should notice is that:
```
5!=5 * 4 * 3 * 2 * 1 but 4*3*2*1 is really 4!
So:

5! = 5* 4!  but 4! is just 4* 3!  and so on.
```

Thus if I had a function that can give me the factorial of any number I can use it to find the factorial of that number-1.  In other words I can use the int factorial(int) function
```c
int factorial(int n){
    int rc;                     //stores result of function
    if(n==1 || n==0){           //check for base case
        rc=1;                   //if n is 1 or 0 rc is 1
    }
    else{                       //else it is recursive case
        rc=n * factorial(n-1);  //rc is n * (n-1)!
    }
    return rc;
}
```
