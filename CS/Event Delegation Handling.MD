# Event Delegation Handling #
```javascript
// Select the HTML element that we want to attach our event listener too.
const buttons = document.getElementsByTagName('button');

const clickHandler = function () {
// Create a 'count' variable which will be a part of the clickHandler function's lexical environment.
  let count = 0;

  // return an inner function which creates closure. 
  return function () {
  
   // Increase the locally scoped 'count' variable by one. 
    count++;
   //Use a template literal to display the 'count' variable onto the button element. 
    this.textContent = `Clicks: ${count}`;
  };
};

// Instead of attaching the event listener to the container holding our buttons, we loop through our buttons and attach an event listener to each one.
// Now each button has a backpack with its own reference to `count` instead of a reference to a global variable or attribute.
// Instead of doing a costly reads on the DOM, we now only mutate the private `count` variable.
for (let i = 0; i < buttons.length; i++) {
  buttons[i].addEventListener('click', clickHandler());
}
```

This example illustrates event handling delegation in JavaScript. Instead of registering an event listener on each individual button, the code registers a single event listener on the collection of buttons as a whole.

The `clickHandler` function is defined as a factory function that returns a new function that increments a count variable and updates the text content of the button that was clicked.

Instead of registering event listeners on each button, the code loops through all buttons, and for each button it attaches the inner function returned by the factory function `clickHandler` as the click event listener.

In this way, when an event is triggered on any of the buttons, the event bubbles up to the parent element (i.e. the collection of buttons) and triggers the event handler on the parent. The event handler then checks the target element of the event (i.e. which button was clicked), and updates its text content accordingly.

Event delegation allows for registering a single event listener that can handle multiple events on multiple elements, making the code more efficient and maintainable. Since the event listener is attached to the container of the buttons, the code can add or remove buttons without needing to add or remove listeners accordingly. Additionally, each button holds its own click count, instead of a global variable or attribute, this reduces DOM reads and only mutates the private `count` variable.