# Linear Search in JavaScript #

Linear search, also known as sequential search, is a method for finding an element within an array or list by iterating through each element one at a time and comparing it to the element we are searching for.

Here's an example:

```javascript
const arr = [1, 2, 3, 4, 5, 6, 7, 8, 9, 7];

// This implementation will identify the first index that holds our searched element and return that index:
const linearSearch = (array, element) => {
  // Loop the given array.
  for (let index = 0; index < array.length; index++) {
    // Check to see if the index of the given array is equal to the element we are searching for.
    if (array[index] === element) {
      // Exit the search by returning the index of the element.
      return index;
    }
  }
  // -1 when no matching element was found in the given array.
  return -1;
};

console.log(linearSearch(arr, 77));
```

This implementation, `linearSearch(arr, element)` takes an array `arr` and an element to search for as arguments. It then uses a for loop to iterate through the array and compares each element to the search element using the equality operator (`===`). If a match is found, the function exits the loop and returns the index of the element in the array by using the `return` keyword. If the element is not found, the function returns -1 after the for loop ends.

```javascript
// A different implementation of this function that will return an array of every index the searched element appears:
const linearSearchMultipleElements = (array, element) => {
  // Create an empty array to store the indexes of the matching elements.
  const elemIndexes = [];

  // Loop the the given array.
  for (let index = 0; index < array.length; index++) {
    // Check to see if the index of the given array is equal to the element we are searching for.
    if (array[index] === element) {
      // Pushes the index of the element we are searching for to the array we created.
      elemIndexes.push(index);
    }
  }

  // Before returning the array of indexes, we first need to check if we have collected any.
  if (elemIndexes.length === 0) {
    return 'Not found';
  } else {
    return elemIndexes;
  }
};

console.log(linearSearchMultipleElements(arr, 77));
```

This implementation, `linearSearchMultipleElements(array, element)` is similar to the first implementation, but instead of returning the index of the first match, it creates an empty array `elemIndexes` to store the indexes of all matching elements and uses the `push()` method to add the indexes of all matches to the array. The function then checks if any matching elements were found by checking the length of the `elemIndexes` array. If no matching elements were found, the function returns 'Not found', otherwise, it returns the array of indexes.

Both of these implementations are examples of linear search, as they iterate through the array one element at a time, comparing each element to the search element, and both have a time complexity of O(n) in the worst case.