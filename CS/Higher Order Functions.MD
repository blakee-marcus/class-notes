# Higher Order Functions in JavaScript #

In JavaScript, a higher-order function is a function that takes one or more functions as arguments and/or returns a function. A higher-order function is a function that operates on other functions, either by taking them as arguments or by returning them.

Here's an example:
```javascript
const grades = [56, 78, 99, 85];

// We receive the accumulator, currentValue, index, and the array from the reduce method.
function findAverage(accumulator, currentValue, index, array) {
  // Check to see if we are at the end of the given array.
  if (index === array.length - 1) {
    // Once we have reached the end of the array we divide by how many elements are in the given array.
    return (accumulator + currentValue) / array.length;
  }

  // Add the current value to our total.
  return accumulator + currentValue;
}

// Pass the 'findAverage' function into the reduce method.
let gradeAverage = grades.reduce(findAverage);

// log the 'gradeAverage' variable to see the result.
console.log(gradeAverage);
```

This example uses the `reduce()` method, which is a higher-order function, to find the average of an array of grades. The `reduce()` method takes a callback function, in this case ``findAverage``, as an argument and applies it to each element of the array.

The `findAverage` function takes four arguments: an accumulator, the currentValue, the index and the array. The `reduce()` method starts by initializing the accumulator to the first element of the array and passing the currentValue to be the second element, and so on.

In this example, the `findAverage` function has the following behavior:

1. It adds the currentValue to the accumulator.
2. It checks if the index is equal to the last element of the array
3. If it is, it returns the accumulated sum of the array divided by the length of the array.
4. If it's not, it returns the accumulator, so that it can be used for next elements.
The `reduce()` method applies the `findAverage` function to the array of grades, accumulating the sum of the grades. At the end of the array, when the last element is reached, the final accumulated sum is divided by the number of elements in the array to find the average.

In this example, the `findAverage` function is a higher-order function because it takes the `reduce` method's callback function as an argument, it uses it to perform operations on array element and returns the desired output.

The `reduce` method is a higher-order function because it takes a callback function as its argument, applies it to the elements of the array and returns the desired output.