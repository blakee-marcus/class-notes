# Implement a stack by using a class in JavaScript #

A stack is a linear data structure that follows the Last In, First Out (LIFO) principle. This means that the last element added to the stack will be the first one to be removed.

Here's an example:
```javascript
class Stack {
  // default value allows stack to initialize without an argument
  constructor(container = []) {
    this.container = container;
  }

  // adds an element to the top of the stack
  addToStack(el) {
    return this.container.push(el);
  }

  // removes an element from the top of the stack
  removeFromStack() {
    return this.container.pop();
  }
}

module.exports = Stack;
```

The Stack class has two main methods: `addToStack()` and `removeFromStack()` that handle the basic operations of a stack: push and pop respectively.

The constructor method of the class takes an optional argument `container`, which is an array that is used to store the elements of the stack. If no argument is passed to the constructor, it defaults to an empty array.

* The `addToStack(el)` method takes an element as an argument and adds it to the top of the stack by using the `push()` method of the array.

* The `removeFromStack()` method removes an element from the top of the stack by using the `pop()` method of the array, which removes the last element from the array and returns it. This corresponds to the element that is at the top of the stack.

This class represents a stack in a simple form and it's useful for understanding the basics of the stack. Also it can be used for basic operations like push and pop, but it does not include peek, isEmpty or other advanced operations, which you may need in a real-world implementation.
Also, it does not check for the maximum size of the stack or handle an overflow condition.

Here is an example of how you might implement a stack with additional methods for peek, isEmpty, and handling overflow conditions in JavaScript:

```javascript
class Stack {
    constructor(maxSize = Infinity) {
        this.container = [];
        this.maxSize = maxSize;
    }

    push(el) {
        if (this.container.length === this.maxSize) {
            throw new Error('Stack overflow');
        }
        this.container.push(el);
    }

    pop() {
        if (this.isEmpty()) {
            throw new Error('Stack underflow');
        }
        return this.container.pop();
    }

    peek() {
        if (this.isEmpty()) {
            return null;
        }
        return this.container[this.container.length - 1];
    }

    isEmpty() {
        return this.container.length === 0;
    }

    get maxStack() {
        return this.maxSize;
    }

    set maxStack(value) {
        this.maxSize = value;
    }
}
```

The Stack class has a constructor method that initializes an empty array as the container for the stack. It also takes an optional parameter maxSize to set the maximum size of the stack. If no argument is passed to the constructor, it defaults to infinity which mean no maxSize.

* The `push(el)` method takes an element as an argument and adds it to the top of the stack. Before pushing it, it checks whether the length of the container array is equal to the maximum size of the stack, if yes it throws a "Stack overflow" error.

* The `pop()` method removes an element from the top of the stack and returns it. Before doing this, it checks if the stack is empty using the `isEmpty()` method, if yes it throws a "Stack underflow" error.

* The `peek()` method returns the top element of the stack without removing it. If the stack is empty it returns null.

* The `isEmpty()` method returns true if the stack is empty, `false` otherwise.

* The `maxStack` getter method returns the maximum size of the stack.

* The `maxStack` setter method sets the maximum size of the stack, it can be used to change the maximum size of the stack after it is created.