# Recursion #

Recursion is a programming technique where a function calls itself in order to solve a problem. It is a way of breaking down a complex problem into smaller, simpler problems that can be solved using the same function.

A recursive function in JavaScript typically has two parts: a base case and a recursive case. The base case is the condition that ends the recursion, and the recursive case is the part of the function that calls itself.

For example, consider the problem of computing the factorial of a number. The factorial of a number n is the product of all the integers from 1 to n. We can solve this problem using recursion as follows:

```javascript
function factorial(n) {
  // Base case: if n is less than or equal to 1, the factorial is 1
  if (n <= 1) {
    return 1;
  }
  // Recursive case: the factorial of n is n multiplied by the factorial of n-1
  return n * factorial(n-1);
}
```

In this example, the base case is when n is less than or equal to 1, in which case the function returns 1. The recursive case is when n is greater than 1, in which case the function calls itself with the argument n-1 and multiplies the result by n. Each time the function is called, it takes a smaller value of n, until it reaches the base case and the recursion ends.

Recursion can be used to solve many different types of problems in JavaScript, including traversing tree data structures, generating permutations and combinations, and solving mathematical problems like the Fibonacci sequence. However, it's important to be aware that recursion can lead to stack overflow if the recursion depth is too deep and also it may be less efficient than using loops.