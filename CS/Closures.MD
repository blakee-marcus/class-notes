# Closures in JavaScript #

In JavaScript, a closure is a function that has access to the variables in its parent scope, even after the parent function has completed executing. Closures allow a function to "remember" the context in which it was created, and maintain access to the variables and functions defined in that context, even after the function has returned.

A closure is created when a function is defined inside another function and the inner function has access to the variables in the outer function's scope.

Here's an example:
```javascript
function counter() {
  // Create a 'count' variable inside of the outer function.
  let count = 0;

  // Return an inner function creating a closure.
  return {
    increment: function () {
      // Increment the outer function's 'count' variable by one.
      return ++count;
    },
  };
}

module.exports = counter;
```

The `counter` function creates a variable `count` with an initial value of 0. It then returns an object with a single property, `increment`, which is a function. The `increment` function increments the value of `count` by 1 and returns it.

When the `counter` function is invoked, it creates a new execution context, which includes the `count` variable. This execution context is then closed over by the `increment` function, which is returned. The `increment` function maintains a reference to the execution context of the parent function, so it can still access the variables defined in the parent scope, even after the `counter` function has completed executing.

Because the `increment` function has access to the `count` variable defined in the parent scope, it can increment the `count` variable each time it is invoked. This allows the `increment` function to maintain its own internal state, which is independent of other instances of the `counter` function.

In this way, the closure allows the `counter` function to define private state and behavior that can be shared across multiple instances, by returning a function that maintains the state of the original execution context.