Binary search is a search algorithm that is used to find an element within a sorted array by repeatedly dividing the search interval in half. It is a more efficient search algorithm than linear search, as it has a time complexity of O(log n) in the average and worst case.

In JavaScript, we can implement binary search using a while loop. The basic idea behind binary search is that we start by selecting the middle element of the array and compare it to the element we are searching for. If the middle element is equal to the search element, we have found the element and can return its index. If the middle element is greater than the search element, we know that the element must be in the left half of the array, so we repeat the process on the left half of the array. If the middle element is less than the search element, we know that the element must be in the right half of the array, so we repeat the process on the right half of the array.

Here is an example of how we can implement binary search in JavaScript:

```javascript
function binarySearch(arr, element) {
  let start = 0;
  let end = arr.length - 1;

  while (start <= end) {
    let middle = Math.floor((start + end) / 2);
    if (arr[middle] === element) {
      return middle;
    } else if (arr[middle] < element) {
      start = middle + 1;
    } else {
      end = middle - 1;
    }
  }
  return -1;
}
```

In this example, the function takes an array `arr` and an element to search for as arguments. It uses a while loop to iterate through the array, starting with the middle element and dividing the array into two parts at each iteration. It uses the comparison operator (`<`) and the equality operator (`===`) to compare the middle element to the search element. If a match is found, the function returns the index of the element in the array. If the element is not found, the function returns -1 after the while loop ends.

It's important to note that the input array must be sorted for binary search to work correctly.