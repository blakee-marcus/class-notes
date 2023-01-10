# Call Back Queue in JavaScript #

In JavaScript, the callback queue is a data structure that holds functions that are waiting to be executed. These functions are called callbacks. These callbacks are usually associated with events or asynchronous operations, such as timers, network requests, or user interactions.

The JavaScript runtime uses the event loop to manage the execution of code. The event loop checks the call stack to see if there are any functions that are currently being executed. If the call stack is empty, it checks the callback queue to see if there are any functions waiting to be executed. If there are, it moves the first function in the callback queue to the call stack and runs it. This process continues until all the functions in the callback queue have been executed.

Callbacks are added to the callback queue when they are passed as arguments to functions such as setTimeout, addEventListener, or XMLHttpRequest.open. Once the associated event or operation has completed, the callback is moved to the callback queue and then eventually moved to the call stack to be executed.

Here's an example of how callbacks are used with setTimeout:
```javascript
console.log('Start');
setTimeout(() => {
    console.log('Timeout callback');
}, 0);
console.log('End');
```
In this example, the callback function passed to setTimeout is not executed immediately. Instead, it's added to the callback queue, and the event loop will execute it after the call stack is empty. The output of this code will be:
```
Start
End
Timeout callback
```
You can see that, setTimeout callback is added to callback queue, and it will be executed later.

It's important to note that the callback queue is separate from the call stack. Callbacks in the callback queue are only executed when the call stack is empty. Also, the order of callbacks in the callback queue is preserved, ensuring that callbacks are executed in the order in which they were added to the queue.