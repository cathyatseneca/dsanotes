# Stack Applications

* Bracket checking
 * int bracketcheck(char expr[]);  returns true if expr is a string where (), {} and [] brackets are properly matched.  false if not.
* Postfix expression calculator
 * The way we write expressions uses infix notation.  In other words, all operations look like A operator B (operation is "in" the middle of the expression).  In order to change the order of operations, we must use ().  Order of operations also matter
 * Another way to write expressions is to use postfix expression.  All operations look like  A B operator
 * The advantage of postfix expressions is that brackets are not needed and order of operators are not needed.
 * Example:  infix (1+2)-3*(4+5), equivalent postfix:  1 2 + 3 4 5 + * -
 * Some calculators actually use postfix notation for entry.
* Infix to postfix converter

