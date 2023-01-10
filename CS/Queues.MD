# Queues in JavaScript #

A queue is a linear data structure that follows the First In, First Out (FIFO) principle. This means that the first element added to the queue will be the first one to be removed.

Here is an example:
```javascript
class Queue {
    constructor() {
        this.items = [];
    }

    enqueue(item) {
        this.items.push(item);
    }

    dequeue() {
        if (!this.isEmpty()) {
            return this.items.shift();
        }
    }

    peek() {
        if (!this.isEmpty()) {
            return this.items[0];
        }
    }

    isEmpty() {
        return this.items.length === 0;
    }
}
```

The Queue class has an initializer method `constructor()` which initializes an empty array to store the items in the queue.
* The `enqueue(item)` method takes an item as an argument and adds it to the end of the array.
* The `dequeue()` method removes and returns the first item of the array (which is the front of the queue). It checks whether the queue is empty before performing the dequeue operation to avoid an error.
* The `peek()` method returns the first item of the array (which is the front of the queue) without removing it.
* The `isEmpty()` method returns true if the queue is empty and false otherwise.