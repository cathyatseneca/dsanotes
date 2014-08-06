#Introduction to Algorithms Analysis

When you write a program or subprogram you should be concerned about the resource needs of the program.  The two main resources are time and memory.  These are separate resources and depending on the situation, you may end up choosing an algorithm that uses more of one resource in order to be more efficient with the other.  Understanding this will allow you to be produce better code.

The amount of resources needs often depends on the amount of data you have.  Intuitively, it makes sense that if you have more data you will need more space to store the data and it will take more time for an algorithm to run. Algorithms Anaylsis does not answer the question "How much resource will be used to process n pieces of data"... the real question it answers is "How much *more* time will it take to process n+1 pieces of data". In other words what we really care about is the growth rate of resources with respect to the data.

And with this in mind, let us now consider some typical growth rates.
